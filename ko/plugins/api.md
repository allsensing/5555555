# 컨텍스트와 API

GitBook 은 플러그인에 다른 API 와 컨텍스트를 제공합니다. 이 API 는 사용되는
GitBook 버전에 따라 달라질 수 있습니다. 그래서 플러그인은 `package.json` 의
`engines.gitbook` 필드를 명시해야합니다.

#### 책 인스턴스

`Book` 클래스는 GitBook 의 중점입니다. 이것은 읽기 메소드에 대한 모든 접근을
집중화합니다. 이 클래스는
[book.js](https://github.com/GitbookIO/gitbook/blob/master/lib/book.js) 에
정의되어 있습니다.

```js
// book.json 에서 설정 읽기
var value = book.config.get('title', 'Default Value');

// 파일 이름을 절대 경로로 변환
var filepath = book.resolve('README.md');

// 인라인 마크업 문자열 표시
book.renderInline('markdown', '이것은 **마크다운**입니다')
    .then(function(str) { ... })

// 마크업 문자열 표시 (블록 방식)
book.renderBlock('markdown', '* 이것은 **마크다운**입니다')
    .then(function(str) { ... })
```

#### 출력 인스턴스

`Output` 클래스는 출력/쓰기 처리를 나타냅니다.

```js
// 출력의 루트 폴더 반환
var root = output.root();

// 출력 폴더의 파일 경로 얻기
var filepath = output.resolve('myimage.png');

// 파일 이름을 웹주소로 변환 (HTML 파일 경로 반환)
var fileurl = output.toURL('mychapter/README.md');

// 출력 폴더에 파일 작성
output.writeFile('hello.txt', 'Hello World')
    .then(function() { ... });

// 출력 폴더에 파일을 복사
output.copyFile('./myfile.jpg', 'cover.jpg')
    .then(function() { ... });

// 파일이 존재하는지 확인
output.hasFile('hello.txt')
    .then(function(exists) { ... });
```

#### 페이지 인스턴스

페이지 인스턴스는 현재 분석된 페이지를 나타냅니다.

```js
// 페이지의 제목 (개요에 있는)
page.title

// 페이지의 내용 (단계에 따른 마크다운/Asciidoc/HTML)
page.content

// 책을 기준으로 한 상대 경로
page.path

// 파일에 대한 절대 경로
page.rawPath

// 이 파일에 사용된 구문 분석기의 종류
page.type ('markdown' 또는 'asciidoc')
```

#### 블록과 필터 컨텍스트

블록과 필터는 같은 컨텍스트에 접근합니다. 이 컨텍스트는 템플릿 엔진 실행과
결합됩니다:

```js
{
    // 현재 템플릿 문법
    "ctx": {
        // 예를 들어, {% set message = "hello" %} 후
        "message": "hello"
    },

    // 책 인스턴스
    "book" <Book>,

    // 출력 인스턴스
    "output": <Output>
}
```

예를 들어 필터 또는 블록 함수는 다음을 사용하여 현재 책에 접근할 수 있습니다:
`this.book`.

#### 훅 컨텍스트

훅은 `this.book` 을 사용해서만 `<Book>` 인스턴스에 접근할 수 있습니다.
