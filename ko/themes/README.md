# 테마

3.0.0 버전 이후 GitBook 은 테마를 쉽게 사용할 수 있습니다. 책은 기본적으로
[theme-default](https://github.com/GitbookIO/theme-default) 테마를 사용합니다.

> **경고**: 사용자 지정 테마는 일부 플러그인을 제대로 동작하지 못하게 할 수
있습니다.

### 테마의 구조

테마는 템플릿과 자산을 포함하는 플러그인입니다. 개인 템플릿 재정의는
선택사항입니다. 테마는 항상 기본 테마를 확장하기 때문입니다.

| 폴더 | 설명 |
| -------- | ----------- |
| `_layouts` | 모든 템플릿을 담고있는 기본 폴더 |
| `_layouts/website/page.html` | 일반 페이지 템플릿 |
| `_layouts/ebook/page.html` | 전자책 생성에 사용되는 일반 페이지 템플릿 (PDF, ePub, Mobi) |


### 책에서 테마 확장/사용자정의 하기

저자가 직접 책 소스에서 (외부 테마를 생성하지 않고) 테마의 템플릿을 확장할 수
있습니다. 템플릿은 먼저 책의 `_layouts` 폴더에서 해결될 것 입니다. 그다음 설치된
플러그인/테마를 사용합니다.

### 분기 대신 확장

여러 책을 변경하는 테마를 만들기 위해 기본 테마를 분기하는 대신
[템플릿 구문](../templating/README.md)을 사용하여 확장할 수 있습니다:

```html
{% extends template.self %}

{% block body %}
    {{ super() }}
    ... 이것은 "body" 블록에 추가될 것 입니다
{% endblock %}
```

보다 완전한 예제는 [API](https://github.com/GitbookIO/theme-api) 테마를 살펴보세요.

### 테마 게시

테마는 `theme-` 접두사를 달고 플러그인으로 게시됩니다
([관련 문서를 보세요](../plugins/README.md)). 예를 들어 `awesome` 테마는
`gitbook-plugin-theme-awesome` NPM 패키지에서 온 `theme-awesome` 플러그인에서
불러질 것 입니다.
