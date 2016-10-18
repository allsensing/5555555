# 필터 확장

필터는 변수에 적용될 수 있는 본질적인 함수입니다. 그것은 파이프 연산 (`|`) 으로
호출되며 인수를 가질 수 있습니다.

```
{{ foo | title }}
{{ foo | join(",") }}
{{ foo | replace("foo", "bar") | capitalize }}
```

### 새 필터 정의

플러그인은 `filters` 범위내의 자신의 진입점에 사용자 정의 함수를 정의하여 필터를
확장할 수 있습니다.

필터 함수는 첫 인수를 필터에 대한 내용으로 받고, 새 내용을 반환해야 합니다.

`this` 와 GitBook API 에 자세히 알아보려면 [컨텍스트와 API](./api.md) 를
참조하세요.

```js
module.exports = {
    filters: {
        hello: function(name) {
            return '안녕 '+name;
        }
    }
};
```

`hello` 필터는 책에서 사용될 수 있습니다:

```
{{ "Aaron"|hello }}, 어떻게 지내니?
```

### 블록 인수 처리

인수는 필터에 전달될 수 있습니다:

```
안녕 {{ "Samy"|fullName("Pesse", man=true}} }}
```

인수는 함수로 전달됩니다. 명명된 인수는 마지막 인수 (객체) 로 전달됩니다.

```js
module.exports = {
    filters: {
        fullName: function(firstName, lastName, kwargs) {
            var name = firstName + ' ' + lastName;

            if (kwargs.man) name = "Mr" + name;
            else name = "Mrs" + name;

            return name;
        }
    }
};
```