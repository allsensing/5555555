# 페이지 및 개요

### 개요

GitBook 은 책의 장과 절의 구조를 정의하는데 `SUMMARY.md` 파일을 사용합니다.
`SUMMARY.md` 파일은 책의 목차를 만드는데 사용됩니다.

`SUMMARY.md` 의 형식은 단지 연결의 목록입니다. 연결의 제목은 장의 제목으로
사용되고 대상은 장의 파일에 대한 경로입니다.

부모 장에 중첩된 목록을 추가하면 절이 생성됩니다.

##### 간단한 예

```markdown
# 개요

* [1 장](part1/README.md)
    * [쓰기는 좋습니다](part1/writing.md)
    * [GitBook 은 좋습니다](part1/gitbook.md)
* [2 장](part2/README.md)
    * [우리는 피드백을 사랑해요](part2/feedback_please.md)
    * [저자를 위한 더 나은 도구](part2/better_tools.md)
```

각 장은 전용 페이지 (`part#/README.md`) 를 가지고 있으며 절로 분할되있습니다.

##### 앵커

목차의 장은 앵커를 사용해서 파일의 특정 부분을 가르킬 수 있습니다.

```markdown
# 개요

### 1 부

* [1 장](part1/README.md)
    * [쓰기는 좋습니다](part1/README.md#writing)
    * [GitBook 은 좋습니다](part1/README.md#gitbook)
* [2 장](part2/README.md)
    * [우리는 피드백을 사랑해요](part2/README.md#feedback)
    * [저자를 위한 더 나은 도구](part2/README.md#tools)
```


##### 부분

목차는 제목 또는 가로줄에 의해 분리된 부분들로 분할할 수 있습니다:

```markdown
# 개요

### 1 부

* [쓰기는 좋습니다](part1/writing.md)
* [GitBook 은 좋습니다](part1/gitbook.md)

### 2 부

* [우리는 피드백을 사랑해요](part2/feedback_please.md)
* [저자를 위한 더 나은 도구](part2/better_tools.md)

----

* [제목없는 마지막 장](part3/title.md)
```

부분은 단지 장의 묶음이며 전용 페이지를 갖지 않습니다. 그러나 테마에 따라 탐색에
표시됩니다.

### 페이지

#### 마크다운 문법

GitBook 에 대한 파일 대부분은 마크다운 문법을 사용합니다. GitBook 은
그것으로부터 페이지의 구조를 유추합니다. 사용 된 문법은
[GitHub 마크다운 문법](https://guides.github.com/features/mastering-markdown/)과
유사합니다. 또한 [AsciiDoc 문법](asciidoc.md)을 선택할 수 있습니다.

##### 장 파일 예제

```markdown
# 장의 제목

이것은 훌륭한 소개입니다.

## 1 절

마크다운이 **책의 구조**의 _대부분_을 지시할 것 입니다.

## 2 절

...

```

#### 서문

페이지는 선택적으로 서문을 가질 수 있습니다. 페이지의 설명을 정의하는데 사용할
수 있습니다. 서문은 파일의 처음에 와야하며 삼중 점선 줄 사이에 유효한 YAML
형식으로 작성되어야 합니다. 기본 예제입니다:

```yaml
---
설명: 이것은 페이지에 대한 간단한 설명입니다.
---

# 페이지의 내용
...
```

서문은 변수를 정의할 수 있습니다. 그것들은
[페이지 변수](templating/variables.md)에 추가될 것이며, 템플릿에서 사용할 수
있습니다.
