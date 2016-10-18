# 변수

다음은 책의 구문 분석과 테마 생성시에 사용할 수 있는 자료의 참조입니다.

### 전역 변수

| 변수 | 설명 |
| -------- | ----------- |
| `book` | 책 전역 정보 + `book.json` 의 구성 설정. 자세한 내용은 아래를 보세요. |
| `gitbook` | GitBook 특정 정보 |
| `page` | 현재 페이지 특정 정보 |
| `file` | 현재 페이지 특정 정보와 연관된 파일 |
| `readme` | Readme 에 대한 정보 |
| `glossary` | 용어사전에 대한 정보 |
| `summary` | 목차에 대한 정보 |
| `languages` | 다국어 책 언어의 목록 |
| `output` | 출력 생성기에 대한 정보 |
| `config` | `book.json` 의 덤프 |

### 책 변수

| 변수 | 설명 |
| -------- | ----------- |
| `book.[CONFIGURATION_DATA]` | `book.json` 을 통해 설정된 모든 `변수들`은 책 변수를 통해 사용가능합니다. |
| `book.language` | 다국어 책에서 현재 언어 |

### GitBook 변수

| 변수 | 설명 |
| -------- | ----------- |
| `gitbook.time` | 현재 시각 (`gitbook` 명령이 실행됐을 때). |
| `gitbook.version` | 책 생성에 사용된 GitBook 의 버전 |

### 파일 변수

| 변수 | 설명 |
| -------- | ----------- |
| `file.path` | 원시 페이지 경로 |
| `file.mtime` | 수정된 시각. 파일이 수정된 마지막 시각 |
| `file.type` | 이 파일을 번역하는데 사용된 구문 분석기의 이름 (예: `markdown`, `asciidoc`, 등) |

#### 페이지 변수

| 변수 | 설명 |
| -------- | ----------- |
| `page.title` | 페이지 제목 |
| `page.previous` | 목차에서 이전 페이지 (`null` 이 될 수 있음) |
| `page.next` | 목차에서 다음 페이지 (`null` 이 될 수 있음) |
| `page.dir` | 글 방향, 설정에 따르거나 내용에서 검출됨 (`rtl` 또는 `ltr`) |

#### 목차 변수

| 변수 | 설명 |
| -------- | ----------- |
| `summary.parts` | 목차에서 부분의 목록 |

전체 목차 (`SUMMARY.md`) 는 접근될 수 있습니다:

`summary.parts[0].articles[0].title` 는 첫 글의 제목을 반환할 것 입니다.

#### 다국어 책 변수

| 변수 | 설명 |
| -------- | ----------- |
| `languages.list` | 이 책의 언어 목록 |

언어는 `{ id: 'en', title: 'English' }` 으로 정의됩니다.

### 출력 변수

| 변수 | 설명 |
| -------- | ----------- |
| `output.name` | 출력 생성기의 이름, 가능한 값은 `website`, `json`, `ebook` 입니다 |
| `output.format` | `output.name == "ebook"` 일때, `format` 은 생성될 전자책 형식을 정의합니다. 가능한 값은 `pdf`, `epub`, `mobi` 입니다 |

### Readme 변수

| 변수 | 설명 |
| -------- | ----------- |
| `readme.path` | 책에서 Readme 경로 |

### 용어사전 변수

| 변수 | 설명 |
| -------- | ----------- |
| `glossary.path` | 책에서 용어사전 경로 |
