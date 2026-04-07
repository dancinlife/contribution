> 🔴 **HEXA-FIRST**: 모든 코드는 `.hexa`로 작성. sh/py/rs 신규 작성 금지. 부하 유발 명령 최소화.

> 🔴 **NEXUS-6 특이점 연동**: 이 프로젝트의 돌파/발견/실험은 nexus 특이점 사이클 입력이다.
> - **돌파 시**: `HEXA=$HOME/Dev/hexa-lang/target/release/hexa && $HEXA $HOME/Dev/nexus/mk2_hexa/native/blowup.hexa <domain> 3 --no-graph`
> - **발견 기록**: `$HOME/Dev/nexus/shared/growth_bus.jsonl`에 JSON append
> - **전체 상태**: `$HEXA $HOME/Dev/nexus/mk2_hexa/native/command_router.hexa "contribution 상태"`

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
