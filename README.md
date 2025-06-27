# 한국전쟁의 숨겨진 역사 번역 및 출판 작업

## `MBBook`을 이용한 웹 서비스

### ✅ mdBook 기본 구조

```bash
repo/
├── book.toml         # 설정 파일 (필수)
└── src/              # 모든 Markdown 파일 위치
    ├── SUMMARY.md    # 목차를 정의 (필수)
    ├── chapter1.md
    ├── chapter2.md
```

### 📁 `book.toml` 예시

```toml
[book]
title = "한국전쟁의 숨겨진 역사"
author = ["I.F. Stone"]
language = "ko"
multilingual = false
src = "src"

[output.html]
# 사이트 스타일 커스터마이징 (선택)
default-theme = "light"
preferred-dark-theme = "navy"
mathjax-support = true
# GitHub에 연결하면 우상단 링크 생성
git-repository-url = "https://github.com/nalutbae/book-the-hidden-history-of-the-korean-war"
```

#### `book.toml` 주요 항목 설명:

| 항목           | 설명                                            |
| -------------- | ----------------------------------------------- |
| `title`        | 책 제목                                         |
| `author`       | 저자 이름 (배열로 여러 명 가능)                 |
| `language`     | 언어 코드 (한국어는 `ko`)                       |
| `multilingual` | 다국어 책인 경우 `true`                         |
| `src`          | Markdown 파일이 있는 폴더 경로 (기본값은 `src`) |

##### `output.html` 항목

| 항목                   | 설명                                    |
| ---------------------- | --------------------------------------- |
| `default-theme`        | 기본 테마 (`light`, `navy`, `rust`, 등) |
| `preferred-dark-theme` | 다크 모드 테마 설정                     |
| `mathjax-support`      | 수식 사용 여부                          |
| `git-repository-url`   | GitHub 링크 버튼 추가                   |

### 🗂️ `src/SUMMARY.md` 예시

책의 **목차와 챕터 구성**은 `SUMMARY.md`로 정의합니다.

```markdown
# Summary

- [서문](ko/preface.md)
  - [브루스 커밍스 서문](ko/preface-cumings.md)
  - [저자 서문](ko/preface-author.md)
- [제1부. 전쟁은 어떻게 시작되었는가](ko/part1.md)
  - [제1장. 그것은 기습이었는가?](ko/chapter1.md)
    ...
- [부록](appendix.md)
```

`SUMMARY.md`는 실제로 Markdown 문서이지만, **목차 역할**을 하기 때문에 링크 형식으로 각 챕터 파일을 나열해야 합니다.

### 🚀 mdBook 사용법 요약

#### 설치

```bash
cargo install mdbook
```

#### 프로젝트 생성

```bash
mdbook init my-book
cd my-book
```

#### 로컬 서버 실행

```bash
mdbook serve
```

브라우저에서 `http://localhost:3000`으로 확인

#### 빌드 (정적 HTML 생성)

```bash
mdbook build
```

결과는 `book/` 디렉토리에 생성됨

### 📝 기타

- 이미지 파일은 `src/images` 폴더에 넣고 Markdown에서 `![설명](images/foo.png)` 형식으로 사용
- `src/` 내에 `README.md`도 만들어두면 기본 페이지로 활용 가능
- `book.css`로 스타일을 커스터마이징하려면 `theme` 디렉토리 사용 가능

### 🔗 공식 문서

- mdBook 공식 사이트: [https://rust-lang.github.io/mdBook/](https://rust-lang.github.io/mdBook/)
- GitHub 리포지토리: [https://github.com/rust-lang/mdBook](https://github.com/rust-lang/mdBook)
