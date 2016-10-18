# 템플릿 생성 도우미 내장

GitBook 을 템플릿 작성을 돕기 위해 내장 필터와 블록의 세트를 제공합니다.

### 필터

`value|default(default, [boolean])`
값이 엄격하게 정의되지 않은 경우 기본값은, 그외는 값을 반환합니다. boolean 이
참이면, 모든 자바스크립트 거짓 값은 기본값을 반환합니다. (false, "", etc)

`arr|sort(reverse, caseSens, attr)`
자바스크립트의 arr.sort 함수로 정렬합니다. reverse 가 참이면, 결과는 반전됩니다.
정렬은 기본적으로 대소문자를 구분하지 않지만, caseSens 를 참으로 설정하면
구분합니다. attr 이 전달되면, 모든 항목과 비교될 것 입니다.

### 블록

`{% markdown %}마크다운 문자열{% endmarkdown %}`
인라인 마크다운 표현

`{% asciidoc %}AsciiDoc 문자열{% endasciidoc %}`
인라인 asciidoc 표현
