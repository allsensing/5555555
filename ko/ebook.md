# 전자책과 PDF 생성

GitBook 은 웹사이트를 생성할 수 있습니다. 그러나 전자책으로도 출력할 수 있습니다
(ePub, Mobi, PDF).

```
# PDF 파일 생성
$ gitbook pdf ./ ./mybook.pdf

# ePub 파일 생성
$ gitbook epub ./ ./mybook.epub

# Mobi 파일 생성
$ gitbook mobi ./ ./mybook.mobi
```

### ebook-convert 설치

`ebook-convert` 은 전자책을 생성하는데 필요합니다 (epub, mobi, pdf).

##### GNU/Linux

[Calibre 애플리케이션](https://calibre-ebook.com/download)을 설치합니다.

```
$ sudo aptitude install calibre
```

일부 GNU/Linux 배포판은 nodejs 라는 이름으로 node 가 설치되어있습니다. 수동으로
심볼릭 링크를 만들어줘야합니다:

```
$sudo ln -s /usr/bin/nodejs /usr/bin/node
```

##### OS X

[Calibre 애플리케이션](https://calibre-ebook.com/download) 다운로드.
애플리케이션 폴더에 `calibre.app` 를 이동한 뒤 ebook-convert 도구의 심볼릭
링크를 만듭니다:

```
$ sudo ln -s ~/Applications/calibre.app/Contents/MacOS/ebook-convert /usr/bin
```

`/usr/bin` 을 $PATH 에 있는 어떠한 디렉토리로도 바꿀 수 있습니다.

### 표지

표지는 모든 전자책 형식에 사용됩니다. 직접 제공하거나
[autocover 플러그인](https://plugins.gitbook.com/plugin/autocover)을 사용하여
생성할 수 있습니다.

표지를 제공하기 위해, 책의 루트 디렉토리에 **`cover.jpg`** 파일을 배치합니다.
**`cover_small.jpg`** 를 추가하면 표지의 작은 버전을 지정합니다. 표지는 **JPEG**
파일이어야합니다.

좋은 표지는 다음과 같은 설명지침을 준수해야합니다:

* `cover.jpg` 는 1800x2360 픽셀 크기로, `cover_small.jpg` 는 200x262 크기로
  합니다
* 테두리가 없어야 합니다
* 책 제목이 잘 보여야 합니다
* 모든 중요한 글자는 작은 버전에서도 보여야합니다
