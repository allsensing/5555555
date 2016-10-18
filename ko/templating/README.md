# 템플릿

GitBook 은 페이지와 테마의 템플릿을 처리하기 위해
[Nunjucks 템플릿 언어](https://mozilla.github.io/nunjucks/)를 사용합니다.

Nunjucks 문법은 **Jinja2** 나 **Liquid** 와 매우 유사합니다. 그 문법은
처리해야할 내용을 표시하기 위해 중괄호 `{ }` 로 둘러쌉니다.

### 변수

변수는 템플릿 컨텍스트에서 값을 찾습니다. 단지 변수를 보여주려한다면,
`{{ 변수 }}` 문법을 사용하면 됩니다. 예시입니다:

```twig
내 이름은 {{ name }} 입니다, 만나서 반갑습니다
```

이것은 컨텐스트에서 사용자 이름을 찾고 보여줍니다. 변수 이름은 자바스크립트처럼
속성을 찾기 위해 점을 가질 수 있습니다. 또한 대괄호 문법을 사용할 수 있습니다.

```twig
{{ foo.bar }}
{{ foo["bar"] }}
```

변수가 정의되지 않았다면, 아무것도 표시되지 않습니다. 다음은 foo 가 정의되지
않았다면 모두 출력되지 않습니다: `{{ foo }}`, `{{ foo.bar }}`,
`{{ foo.bar.baz }}`.

GitBook 은 컨텍스트에서 [미리 정의된 변수](variables.md) 세트를 제공합니다.

### 필터

필터는 변수에 적용될 수 있는 본질적인 함수입니다. 그것은 파이프 연산 (`|`) 으로
호출되며 인수를 가질 수 있습니다.

```twig
{{ foo | title }}
{{ foo | join(",") }}
{{ foo | replace("foo", "bar") | capitalize }}
```

세번재 예제는 어떻게 필터를 연계하는지 보여줍니다. 처음 "foo" 를 "bar" 로 바꾸고
대문자화 해서 "Bar" 를 표시합니다.

### 태그

##### if

`if` 는 조건을 평가하고 내용을 선택적으로 보여줄 수 있게 합니다. 자바스크립트의
`if` 와 정확히 같은 작동을 합니다.

```twig
{% if variable %}
  그것은 참
{% endif %}
```

변수가 정의되 있고 참으로 평가된다면, "그것은 참" 이 표시될 것 입니다. 그외는,
아무일도 일어나지 않습니다.

`elif` 와 `else` 로 다른 조건을 명시할 수 있습니다:

```twig
{% if hungry %}
  나는 배고픕니다
{% elif tired %}
  나는 피곤합니다
{% else %}
  나는 괜찮습니다!
{% endif %}
```

##### for

`for` 는 배열과 사전을 반복합니다.

```twig
# GitBook 에 대한 장

{% for article in glossary.terms['gitbook'].articles %}
* [{{ article.title }}]({{ article.path }})
{% endfor %}
```

##### set

`set` 은 변수를 생성하고 수정할 수 있게합니다.

```twig
{% set softwareVersion = "1.0.0" %}

현재 버전은 {{ softwareVersion }} 입니다.
[내려받기](website.com/download/{{ softwareVersion }})
```

##### 포함과 블록

포함과 상속은 [내용 참조](conrefs.md) 절에 자세히 설명되어 있습니다.

### 탈출

GitBook 이 모든 특수 템플릿 태그를 무시하길 바란다면, raw 를 사용할 수 있습니다.
그 안의 모든 것은 일반 문자열로 출력될 것 입니다.

``` twig
{% raw %}
  이것은 {{ 처리되지 않을 것 }} 입니다
{% endraw %}
```
