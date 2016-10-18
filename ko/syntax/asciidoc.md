# AsciiDoc

`2.0.0` 버전 이후, GitBook 은 입력 형식으로 AsciiDoc 도 지원합니다.

형식에 대한 자세한 내용은
[AsciiDoc 문법 빠른 안내서](http://asciidoctor.org/docs/asciidoc-syntax-quick-reference/)를
참조하세요.

마크다운과 같이, GitBook 은 구조를 추출하기 위해 몇몇 특별한 파일을 사용합니다:
`README.adoc`, `SUMMARY.adoc`, `LANGS.adoc` and `GLOSSARY.adoc`.

### README.adoc

이것은 책의 주요 항목입니다: 소개. 이 파일은 **필수**입니다.

### SUMMARY.adoc

이 파일은 장과 절의 목록을 정의합니다. 마크다운과 같이, `SUMMARY.adoc` 의 형식은
단순히 연결의 목록입니다. 연결의 이름은 장의 이름으로 사용되고, 대상은 장의
파일에 대한 경로입니다.

절은 부모장에 포함된 목록을 추가하는 것으로 간단히 정의할 수 있습니다.

```asciidoc
= 개요

. link:chapter-1/README.adoc[1장]
.. link:chapter-1/ARTICLE1.adoc[1절]
.. link:chapter-1/ARTICLE2.adoc[1절]
... link:chapter-1/ARTICLE-1-2-1.adoc[1.2.1절]
. link:chapter-2/README.adoc[2장]
. link:chapter-3/README.adoc[3장]
. link:chapter-4/README.adoc[4장]
.. Unfinished article
. Unfinished Chapter
```

### LANGS.adoc

[다국어](./languages.md)책을 위해, 이 파일은 지원되는 언어와 번역의 다른점을
정의하는데 사용됩니다.

이 파일은 `SYMMARY.adoc` 와 같은 문법을 사용합니다:

```asciidoc
= 언어

. link:en/[English]
. link:ko/[한국어]
. link:fr/[French]
```

### GLOSSARY.adoc

이 파일은 용어를 정의하는데 사용됩니다. [용어사전 절을 보세요](./lexicon.md).

```asciidoc
= 용어 사전

== Magic

관찰자의 이해를 넘어 경이로운 감각을 생산하는, 충분히 고급 기술입니다.

== PHP

페이스북같은 큰 웹사이트에서 많이 사용되는 대중적인 웹 프로그래밍 언어.
Rasmus Lerdorf 가 1994년에 그의 개인 홈페이지를 제작하기 위해 PHP 을
만들었습니다 (PHP 는 처음 "Personal Home Page" 의 약자였지만 지금은
"PHP: Hypertext Preprocessor" 를 나타냅니다).
```
