# 훅

훅은 사용자 정의 콜백으로 프로세스의 동작을 보강하거나 변경하는 방법입니다.

### 훅의 목록

### 전역 파이프라인과 연관된 것

| 이름 | 설명 | 인수 |
| ---- | ----------- | --------- |
| `init` | 책을 분석한 후에, 출력과 페이지를 생성하기 전에 호출됩니다. | 없음 |
| `finish:before` | 페이지를 생성한 후에, 자산, 표지, 등을 복사하기 전에 호출됩니다. | 없음 |
| `finish` | 모든 것이 끝난 후 호출됩니다. | 없음 |

### 페이지 파이프라인과 연관된 것

> 페이지 분석을 확장하는데 [템플릿](./templating.md) 사용을 권장합니다.

| 이름 | 설명 | 인수 |
| ---- | ----------- | --------- |
| `page:before` | 페이지에서 템플릿 엔진을 실행하기 전에 호출됩니다. | 페이지 객체 |
| `page` | 페이지를 출력하고 색인하기 전에 호출됩니다. | 페이지 객체 |

##### 페이지 객체

```js
{
    // 구문 분석기 이름
    "type": "markdown",

    // 책 루트에 대한 파일의 상대 경로
    "path": "page.md",

    // 파일의 절대 경로
    "rawpath": "/usr/...",

    // 개요에서 페이지의 제목
    "title": "",

    // 페이지의 내용
    // "page:before" 의 마크다운/Asciidoc
    // "page" 의 HTML
    "content": "# Hello"
}
```

##### 제목 추가 예시

`page:before` 훅에서, `page.content` 는 마크다운/AsciiDoc 내용입니다.

```js
{
    "page:before": function(page) {
        page.content = "# 제목\n" +page.content;
        return page;
    }
}
```

##### 몇몇 HTML 을 대체하는 예시

`page` 훅에서, `page.content` 는 마크다운/AsciiDoc 변환으로 생성된 HTML 입니다.

```js
{
    "page": function(page) {
        page.content = page.content.replace("<b>", "<strong>")
            .replace("</b>", "</strong>");
        return page;
    }
}
```


### 비동기 작업

훅 콜백은 비동기로 처리하고 프로미스를 반환할 수 있습니다.

예시:

```js
{
    "init": function() {
        return writeSomeFile()
        .then(function() {
            return writeAnotherFile();
        });
    }
}
```
