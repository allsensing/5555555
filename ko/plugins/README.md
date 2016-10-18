# 플러그인

플러그인은 GitBook 의 기능을 확장하는 가장 좋은 방법입니다 (전자책과 웹사이트).
많은 것을 하는 플러그인이 존재합니다: 수학 공식 표시 지원, Google 웹로그 분석을
사용한 방문자 추적, 등.

### 플러그인은 어떻게 찾나요?

플러그인은 [plugins.gitbook.com](https://plugins.gitbook.com) 에서 쉽게 찾을 수
있습니다.

### 플러그인을 어떻게 설치하나요?

설치하려는 플러그인을 찾았으면, `book.json` 에 그것을 추가해야합니다:

```
{
    "plugins": ["myPlugin", "anotherPlugin"]
}
```

또한 사용하고자하는 특정 버전을 명시할 수 있습니다: `"myPlugin@0.3.1"`.
기본적으로 GitBook 은 현재 GitBook 버전과 호환되는 가장 마지막 버전의 플러그인을
찾을 것 입니다.

### GitBook.com

플러그인은 [GitBook.com](https://www.gitbook.com) 에서 자동으로 설치됩니다.
로컬에서, 책을 위한 모든 플러그인을 설치하고 준비하기 위해 `gitbook install`
명령을 실행하세요.

### 플러그인 구성

플러그인 특정 설정은 `pluginsConfig` 에 저장됩니다. 가능한 옵셜에 대한 자세한
내용은 플러그인 자체 문서를 참조해야합니다.
