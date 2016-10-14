# 구성

GitBook 은 유연한 설정을 사용하여 책을 사용자 정의 할 수 있습니다. 이 옵션은
`book.json` 에 지정되어 있습니다. JSON 구문에 익숙하지 않은 저자는
[JSONlint](http://jsonlint.com) 와 같은 도구를 사용하여 구문의 유효성을 검사 할
수 있습니다.

### 일반 설정

| 변수 | 설명 |
| -------- | ----------- |
| `root` | `book.json` 을 제외한 모든 책의 파일을 포함하는 루트 폴더의 경로. |
| `structure` | Readme, 개요, 용어 등의 경로 명시. [구조 단락](#structure)을 보세요. |
| `title` | 책의 제목이며 기본값은 README 에서 추출됩니다. GitBook.com 에서 이 필드는 미리 채워져있습니다. |
| `description` | 책의 설명이며 기본값은 README 에서 추출됩니다. GitBook.com 에서 이 필드는 미리 채워져있습니다. |
| `author` | 저자의 이름. GitBook.com 에서 이 필드는 미리 채워져있습니다. |
| `isbn` | 책의 ISBN |
| `language` | 책 언어의 [ISO 코드](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)이며 기본값은 `en` 입니다. |
| `direction` | 글자의 방향. `rtl` 또는 `ltr` 이 올 수 있으며, 기본값은 `language` 값에 의존합니다. |
| `gitbook` | 사용되어야하는 GitBook 의 버전. [SemVer](http://semver.org) 사양을 사용하고 `">= 3.0.0"` 같은 조건을 허용합니다. |

### 플러그인

플러그인과 그 설정은 `book.json` 에 지정되어 있습니다. 자세한 내용은
[플러그인 절](plugins/README.md)을 보세요.

3.0.0 버전 이후 GitBook 은 테마를 사용할 수 있습니다. 자세한 내용은
[테마 절](themes/README.md)을 보세요.

| 변수 | 설명 |
| -------- | ----------- |
| `plugins` | 불러올 플러그인의 목록 |
| `pluginsConfig` | 플러그인에 대한 구성 |

### 구조

`root` 변수 외에도 Readme, 요약, 용어, 언어 파일의 이름을 Gitbook 에 알려줄 수
있습니다 (`README.md` 같은 기본 이름을 사용하는 대신). 이 파일은 책의 루트에
있어야 합니다 (또는 각 언어별 책의 루트). `dir/MY_README.md` 같은 경로는
허용되지 않습니다.

| 변수 | 설명 |
| -------- | ----------- |
| `structure.readme` | Readme 파일명 (기본값 `README.md`) |
| `structure.summary` | 개요 파일명 (기본값 `SUMMARY.md`) |
| `structure.glossary` | 용어 파일명 (기본값 `GLOSSARY.md`) |
| `structure.languages` | 언어 파일명 (기본값 `LANGS.md`) |

### PDF 옵션

PDF 출력은 `book.json` 옵션 세트를 사용하여 사용자 정의 할 수 있습니다:

| 변수 | 설명 |
| -------- | ----------- |
| `pdf.pageNumbers` | 각 페이지 하단에 페이지 번호 추가 (기본값 `true`) |
| `pdf.fontSize` | 기본 글꼴 크기 (기본값 `12`) |
| `pdf.fontFamily` | 기본 글꼴 (기본값 `Arial`) |
| `pdf.paperSize` | 용지 크기, 다음값 중 하나 `'a0', 'a1', 'a2', 'a3', 'a4', 'a5', 'a6', 'b0', 'b1', 'b2', 'b3', 'b4', 'b5', 'b6', 'legal', 'letter'` (기본값 `a4`) |
| `pdf.margin.top` | 상단 여백 (기본값 `56`) |
| `pdf.margin.bottom` | 하단 여백 (기본값 `56`) |
| `pdf.margin.right` | 우측 여백 (기본값 `62`) |
| `pdf.margin.left` | 좌측 여백 (기본값 `62`) |
