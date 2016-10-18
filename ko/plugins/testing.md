# 플러그인 테스트

### 로컬에서 플러그인 테스트하기

플러그인을 게시하기 전에 책에서 테스트하는 것은
[npm link](https://docs.npmjs.com/cli/link) 를 사용하면 가능합니다.

플러그인의 폴더에서, 실행합니다:

```
$ npm link
```

책의 폴더에서 실행합니다:

```
$ npm link gitbook-plugin-<플러그인의 이름>
```

### Travis 에서 단위 테스트 하기

[gitbook-tester](https://github.com/todvora/gitbook-tester) 는 플러그인 테스트를
위한 **Node.js/Mocha** 단위 테스트를 작성하기 쉽게 해줍니다.
[Travis.org](https://travis.org) 를 사용하면, 매 커밋/태그 마다 테스트가 실행될
수 있습니다.
