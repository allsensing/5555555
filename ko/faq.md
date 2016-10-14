# GitBook 자주하는질문

이 페이지에 GitBook 형식과 툴체인에 관한 일반적인 질문과 답변을 모았습니다.

GitBook.com 과 편집기에 대한 질문은
[help.gitbook.com 의 자주하는질문](http://help.gitbook.com/faq.html)에 있습니다.

#### 어떻게 내 책을 호스팅/출판합니까?

책은 [GitBook.com](https://www.gitbook.com)에서 쉽게 출판되고 제공될 수 있습니다.
그러나 GitBook 출력은 다른 정적 파일 호스팅 솔루션에서도 제공될 수 있습니다.

#### 내용을 편집하기위해 무엇을 사용할 수 있습니까?

어떠한 텍스트 편집기든 작동합니다! 그러나 우리는
[GitBook 편집기](https://www.gitbook.com/editor)를 권합니다.
[GitBook.com](https://www.gitbook.com) 은 또한 이 편집기의 웹 버전을 제공합니다.

---

#### GitBook 은 우횡서/양방향 글자를 지원합니까?

GitBook 형식은 우횡서와 양방향 쓰기를 지원합니다. 그것을 사용하려면
`book.json` 에 언어 (예: `ar`) 를 지정하거나 GitBook 이 우횡서를 사용하도록
강제할 수 있습니다:

``` json
{
    "language": "ar",
    "direction": "rtl"
}
```

GitBook 의 3.0 버전을 사용하면 내용에 따라 자동 검출합니다.
_책 출력은 정말 우횡서를 존중하지만, 편집기는 아직 우횡서 쓰기를 지원하지 않음을 참고하세요_.

#### 링크에 `.html` 또는 `.md` 확장자를 사용해야합니까?

파일을 연결할 때 항상 경로와 `.md` 확장자를 사용해야합니다. GitBook 은 가르키는
파일이 목차에서 참조될 때 자동으로 이 경로를 해당 연결로 대체합니다.

#### 내 저장소의 하위 디렉토리에 GitBook 을 만들 수 있습니까?

네, GitBook 은 [하위 디렉토리](structure.md#subdirectory)에 만들어질 수 있습니다.
GitBook.com and the CLI also looks by default in a serie of [folders](structure.md).

#### GitBook 은 우횡서 언어를 지원합니까?

네, GitBook 은 페이지의 방향을 자동으로 검출하고 (`rtl` 또는 `ltr`) 그에 따라
레이아웃을 조정합니다. 방향은 또한 [book.json](config.md) 에 전역으로 명시될 수
있습니다.

---

#### GitBook 은 수학 방정식을 지원합니까?

GitBook 은 플러그인덕분에 수학 방정식과 TeX 를 지원합니다. 현재 수학을 표시하는
2개의 공식 플러그인이 있습니다:
[mathjax](https://plugins.gitbook.com/plugin/mathjax) 와
[katex](https://plugins.gitbook.com/plugin/katex).

#### 출력을 사용자 정의하거나 테마를 입힐 수 있습니까?

네, 웹사이트와 전자책 출력 모두 [테마](themes/README.md)로 사용자 정의 할 수
있습니다.

#### 상호작용하는 내용을 추가할 수 있습니까 (비디오, 기타)?

GitBook 은 매우 [유연합니다](plugins/README.md).
[기존 플러그인](https://plugins.gitbook.com)을 사용하거나 직접 만들어보세요!
