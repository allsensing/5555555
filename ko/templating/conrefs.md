# 내용 참조

내용 참조 (conref) 는 다른 파일 또는 책의 내용을 재사용하기 위한 편리한
방법입니다.

### 로컬 파일 가져오기

`include` 태그를 사용하면 다른 파일의 내용을 가져오는 것이 매우 간단합니다:

```
{% include "./test.md" %}
```

### 다른 책에서 파일 가져오기

GitBook 은 git 을 사용하여 포함 경로를 해결할 수 있습니다:

```
{% include "git+https://github.com/GitbookIO/documentation.git/README.md#0.0.1" %}
```

git 웹주소의 형식입니다:

```
git+https://user@hostname/owner/project.git/file#commit-ish
```

실제 git 웹주소 부분은 `.git` 으로 끝나야 합니다. 가져올 파일 이름을 `.git` 뒤에서
추출합니다.

`commit-ish` 는 `git checkout` 의 인수로 제공될 수 있는 모든 태그, sha, 브랜치가
될 수 있습니다. 기본값은 `master` 입니다.

### 상속

템플릿 상속은 템플릿 재사용을 쉽게하는 방법입니다. 템플릿을 작성할 때, 자식
템플릿이 대체할 수 있는 "블록" 을 정의할 수 있습니다. 상속 연계는 원하는 만큼 할
수 있습니다.

`block` 은 템플릿에 구획을 정의하고 이름으로 구분합니다. 기본 템플릿은 블록을
명시할 수 있고 자식 템플릿은 새로운 내용으로 대체할 수 있습니다.

```
{% extends "./mypage.md" %}

{% block pageContent %}
# 이것은 내 페이지 내용입니다
{% endblock %}
```

`mypage.md` 에서, 확장할 수 있는 블록을 명시해야 합니다:

```
{% block pageContent %}
이것은 기본 내용입니다.
{% endblock %}

# 허가서

{% include "./LICENSE" %}
```
