# GitBook 설치 및 설정

GitBook 을 설치하고 사용하는데에는 몇 분 안걸립니다.

### GitBook.com

[GitBook.com](https://www.gitbook.com) 은 책을 작성, 게시, 출판하는 솔루션을
사용하기 쉽게 해줍니다. 귀하의 글과 공동 집필서를 게시하기위한 가장 쉬운
솔루션입니다.

그것은 [GitBook 편집기](https://www.gitbook.com/editor)와 잘 동합되어 있습니다.

### 로컬 설치

##### 요구사항

GitBook 설치는 쉽고 간단합니다. 시스템이 이 두가지 요구사항만 만족하면 됩니다:

* NodeJS (v4.0.0 이상 권장)
* Windows, Linux, Unix, Mac OS X

##### NPM 을 통해 설치

GitBook 을 설치하는 가장 좋은 방법은 **NPM** 을 통하는 것 입니다. 터미널
프롬프트에서 다음 명령을 실행하는 것으로 간단히 GitBook 을 설치합니다:

```
$ npm install gitbook-cli -g
```

`gitbook-cli` 은 한 시스템에서 다양한 버전의 GitBook 을 설치하고 사용할 수 있게
해주는 도구입니다. 책을 구성하는데 필요한 버전의 GitBook 을 자동으로 설치해줄 것
입니다.

##### 책 만들기

GitBook 은 책의 보일러플레이트를 설정할 수 있습니다:

```
$ gitbook init
```

새 디렉토리에 책을 만드려면 `gitbook init ./directory` 명령을 실행하면됩니다.

미리보기 및 책 제공:

```
$ gitbook serve
```

또는 정적 웹사이트 생성:

```
$ gitbook build
```

##### Install pre-releases

`gitbook-cli` 는 책을 테스트하기 위해 GitBook 의 다른 버전을 다운로드하고
설치하기 쉽게 해줍니다:

```
$ gitbook fetch beta
```

`gitbook ls-remote` 명령을 사용하면 원격지의 설치가능한 버전을 나열합니다.

##### 디버깅

`--log=debug` 와 `--debug` 옵션을 사용해서 더 나은 오류 메시지를 얻을 수
있습니다 (스택 추적 포함). 사용예:

```
$ gitbook build ./ --log=debug --debug
```

