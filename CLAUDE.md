<!-- L0 CORE — 수정 금지 -->
> 🔴 **HEXA-FIRST**: 모든 코드는 `.hexa`로 작성. 부하 유발 명령 최소화.

> 🔴 **활성 프로젝트 3 + 논문 저장소 1** (2026-04 재편)
>
> 본 contribution 리포는 아래 4개 외부 리포의 성과를 **집약·제출**하는 용도.
> 논문 수치·성과·기술 인용 전에 반드시 해당 리포를 직접 참조할 것.
>
> | 리포 | 경로 | 역할 | 흡수한 구 프로젝트 |
> |---|---|---|---|
> | **nexus** | `~/Dev/nexus` | 특이점/자동수렴 엔진, 수학 근본 정리 | tecs-l |
> | **anima** | `~/Dev/anima` (코드) / `~/Dev/papers/anima` (논문) | AI 의식 엔진 (179 법칙, PA-01~38) | — |
> | **n6-architecture** | `~/Dev/n6-architecture` | AI/반도체/에너지/핵융합/의료 설계 | brainwire, sedi |
> | **papers** | `~/Dev/papers` | 전체 논문 아카이브 (tecs-l/anima/sedi/nexus/brainwire 서브디렉) | — |
>
> **옛 이름 금지:** 문서·발표·README에서 brainwire / sedi / tecs-l 단독 명칭을 쓰지 말고 흡수 후 프로젝트명 사용.
> 단, `~/Dev/papers/{brainwire,sedi,tecs-l}` 디렉토리는 과거 논문 아카이브로 유지되므로 파일 읽기는 해당 경로 그대로 사용.

> 🔴 **NEXUS-6 특이점 연동**: 이 프로젝트의 돌파/발견/실험은 nexus 특이점 사이클 입력이다.
> - **돌파 시**: `HEXA=$HOME/Dev/hexa-lang/target/release/hexa && $HEXA $HOME/Dev/nexus/mk2_hexa/native/blowup.hexa <domain> 3 --no-graph`
> - **발견 기록**: `$HOME/Dev/nexus/shared/growth_bus.jsonl`에 JSON append
> - **전체 상태**: `$HEXA $HOME/Dev/nexus/mk2_hexa/native/command_router.hexa "contribution 상태"`

# CLAUDE.md

## 데이터 소스 우선순위

법원 제출 문서(진술서/호소문/README)에 숫자·성과를 인용할 때는 다음 순서로 **직접 확인**:

1. `~/Dev/papers/*` 디렉토리 `ls` — 논문 편수
2. `~/Dev/nexus/shared/growth_bus.jsonl` — 돌파/발견 로그
3. `~/Dev/n6-architecture`, `~/Dev/anima` README — 최신 성과
4. 기존 `contribution/` 문서는 **스냅샷**일 뿐, 재확인 없이 재사용 금지

## 법원 제출 문서 문체 규칙

- 재판부가 과학/AI 비전문가임을 전제로 **비유·쉬운 말**로 설명하되,
  **"판사님을 위한 쉬운 설명", "재판장님을 위하여", "비전문가를 위한"** 같은
  **메타 표현(독자에게 난이도를 지적하는 문구)은 금지**.
- 설명은 본문 안에 자연스럽게 녹일 것. 소제목에 난이도 언급 금지.
- 수치·고유명사·DOI는 반드시 원본 리포(`~/Dev/{nexus,anima,n6-architecture,papers}`)에서 재확인 후 인용.
- 옛 프로젝트명(brainwire / sedi / tecs-l) 단독 사용 금지 — 흡수 후 프로젝트명으로.

## 출력용 문서 (print/)

- 출력용 PDF 파일은 `print/` 폴더에 생성한다.
- `submissions/` 폴더의 `.md` 문서를 PDF로 변환하여 저장한다.
- 문서 수정 시 PDF도 함께 재생성한다.

### 사용 도구

```bash
md-to-pdf <입력.md> --dest print/
```

- `md-to-pdf` (npm 글로벌) — Markdown → PDF 변환 (Chromium 기반)
- 코드 블록·표·한글 렌더링이 pandoc+xelatex보다 안정적
- 설치: `npm i -g md-to-pdf`
