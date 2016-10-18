# 플러그인을 만들고 게시하기

GitBook 플러그인은 다음 정의된 규칙에 따라 NPM 에 게시된 노드 패키지입니다.

## 구조

#### package.json

`package.json` 은 **Node.sj 모듈**을 설명하기 위한 목록 형식입니다. GitBook
플러그인은 Node 모듈의 상단에 내장되어 있습니다. 그것은 GitBook 에서 플러그인을
실행하는데 필요한 의존성, 버전, 소유권, 기타정보를 선언합니다. 이 문서는 세부
스키마를 설명합니다.

플러그인을 설명하는 `package.json` 은 또한 필요한 설정에 대한 세부사항을 포함할
수 있습니다. 설정 스키마는 `package.json` 의 `gitbook` 필드에 선언됩니다.
(이 필드는 [JSON 스키마](http://json-schema.org) 설명지침을 따릅니다):

```js
{
    "name": "gitbook-plugin-mytest",
    "version": "0.0.1",
    "description": "이것은 내 첫 GitBook 플러그인입니다",
    "engines": {
        "gitbook": ">1.x.x"
    },
    "gitbook": {
        "properties": {
            "myConfigKey": {
                "type": "string",
                "default": "기본값입니다",
                "description": "나의 멋진 설정을 정의합니다!"
            }
        }
    }
}
```

`package.json` 에 대한 자세한 내용은
[NPM 문서](https://docs.npmjs.com/files/package.json)에 있습니다.

**패키지 이름**은 `gitbook-plugin-` 으로 시작해야하며 **패키지 엔진**은
`gitbook` 을 포함하여야합니다.

#### index.js

`index.js` 는 플러그인 실행 시간의 주 진입점입니다:

```js
module.exports = {
    // Map of hooks
    hooks: {},

    // Map of new blocks
    blocks: {},

    // Map of new filters
    filters: {}
};
```

## 플러그인 게시

GitBook 플러그인은 [NPM](https://www.npmjs.com) 에 게시될 수 있습니다.

새 플러그인을 게시하기 위해, [npmjs.com](https://www.npmjs.com) 에서 계정을
생성하며 명령줄에서 그것을 게시합니다:

```
$ npm publish
```

## 비공개 플러그인

비공개 플러그인은 GitHub 에서 호스팅 될 수 있고 `git` 웹주소를 사용해 포함될 수
있습니다:

```
{
    "plugins": [
        "myplugin@git+https://github.com/MyCompany/mygitbookplugin.git#1.0.0"
    ]
}
```
