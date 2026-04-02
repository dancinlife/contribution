# CLAUDE.md

## 출력용 문서 (print/)

- 출력용 PDF 파일은 `print/` 폴더에 생성한다.
- `submissions/` 폴더의 `.md` 문서를 PDF로 변환하여 저장한다.
- 문서 수정 시 PDF도 함께 재생성한다.

### 사용 도구

```bash
export PATH="/Library/TeX/texbin:$PATH"
pandoc <입력.md> -o print/<출력.pdf> --pdf-engine=xelatex -V mainfont="AppleGothic" -V geometry:margin=2.5cm
```

- `pandoc` — Markdown → PDF 변환
- `xelatex` — PDF 엔진 (한글 지원)
- `AppleGothic` — 한글 폰트
- BasicTeX (`brew install --cask basictex`)
