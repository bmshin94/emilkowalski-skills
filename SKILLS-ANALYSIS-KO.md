# emilkowalski-skills 전수조사 분석 정리 (한국어)

> 작성일: 2026-10-08
> 작성: Claude Code (카리나 페르소나 세션)
> 대상 저장소: <https://github.com/bmshin94/emilkowalski-skills>
> 원본(업스트림): <https://github.com/emilkowalski/skills>
> 원저작자 사이트: <https://emilkowal.ski> / <https://aiforui.dev>
> 라이선스: MIT (© 2026 Emil Kowalski)

---

## 목차

1. [한 줄 정의](#1-한-줄-정의)
2. [저장소 정체 확인](#2-저장소-정체-확인)
3. [파일 전수조사](#3-파일-전수조사)
4. [14개 스킬 상세](#4-14개-스킬-상세)
5. [설계상 뛰어난 점](#5-설계상-뛰어난-점)
6. [핵심 규칙 요약](#6-핵심-규칙-요약)
7. [나에게 주는 도움](#7-나에게-주는-도움)
8. [Q&A 7문 7답](#8-qa-7문-7답)
9. [수익화 아이디어 7가지](#9-수익화-아이디어-7가지)
10. [실행 로드맵](#10-실행-로드맵)
11. [한계와 주의사항](#11-한계와-주의사항)
12. [참고 링크](#12-참고-링크)

---

## 1. 한 줄 정의

> **AI 에이전트에게 "UI 디자인 감각(taste)"을 이식하는 마크다운 지식 팩**

- 실행 코드가 **단 한 줄도 없음**. `.js` / `.ts` / `.json` / `.yaml` 전부 없음
- **마크다운 문서 22개**(skills 내부) + 루트 문서 5개로만 구성
- 프로그램이 아니라 **AI가 읽는 전문가 매뉴얼**

---

## 2. 저장소 정체 확인

| 항목 | 내용 |
|---|---|
| 원저작자 | **Emil Kowalski** — Vercel / Linear 출신 디자인 엔지니어 |
| 대표작 | **Sonner** (주간 npm 다운로드 1,300만+ 토스트 라이브러리), **Vaul** (드로어) |
| 내 저장소 | `bmshin94/emilkowalski-skills` (원본의 포크) |
| 원본 저장소 | `emilkowalski/skills` |
| 총 커밋 수 | 56개 (대부분 Emil 작성) |
| 내가 추가한 커밋 | `aa0d84d` — `CLAUDE.md`, `GEMINI.md`(카리나 페르소나), `.pl`(빈 파일) |
| 라이선스 | **MIT** — 상업적 이용/수정/재배포/판매 모두 허용 (저작권 고지 유지 조건) |
| 작업 브랜치 | `claude/bold-planck-4q58q8` |

---

## 3. 파일 전수조사

### 3.1 루트 파일

| 파일 | 줄 수 | 내용 |
|---|---|---|
| `README.md` | 57 | 설치법 + 14개 스킬 목록. "에이전트는 taste가 없다"가 핵심 주장 |
| `performance-cheatsheet.md` | 15 | 애니메이션 성능 문제 7개 → 해결책 표 (초압축판) |
| `LICENSE` | 21 | MIT, © 2026 Emil Kowalski |
| `.gitattributes` | 2 | GitHub 언어 통계에 `skills/**/*.md` 포함 설정 |
| `CLAUDE.md` | 21 | 카리나 페르소나 (내가 추가, 원본에 없음) |
| `GEMINI.md` | 21 | 동일 페르소나의 Gemini CLI 버전 (내가 추가) |
| `.pl` | 0 | 빈 파일, 용도 불명 |

### 3.2 `skills/` 디렉터리 구조

각 스킬 = 폴더 1개. 폴더 안에 `SKILL.md`(진입점) + 필요시 참조 문서.

```
skills/
├── animate/                     SKILL.md(207) + RECIPES.md(324)
├── animate-expo/                SKILL.md(263) + RECIPES.md(385)
├── animation-vocabulary/        SKILL.md(181)
├── apple-design/                SKILL.md(290)
├── ask-sonner/                  SKILL.md(88)  + API.md(64)
├── break-ui/                    SKILL.md(175) + CATALOG.md(135)
├── emil-design-eng/             SKILL.md(674)  ← 최대 파일
├── find-animation-opportunities/ SKILL.md(140)
├── improve-animations/          SKILL.md(109) + AUDIT.md(115) + PLAN-TEMPLATE.md(73)
├── mobile-native/               SKILL.md(311)
├── pick-ui-library/             SKILL.md(85)
├── prototype/                   SKILL.md(98)  + PICKER.md(197)
├── review-animations/           SKILL.md(120) + STANDARDS.md(187)
└── write-swift/                 SKILL.md(396)

총 마크다운 4,734줄
```

### 3.3 `SKILL.md` 공통 포맷

```markdown
---
name: animate
description: Build an animation from scratch... (AI가 이걸 읽고 발동 여부 판단)
disable-model-invocation: true   # 있으면 수동 호출 전용
---

# Building Animations

## Initial Response
(스킬이 처음 켜질 때 출력할 고정 문장)

## Operating Posture
(어떤 역할로 행동할지 + 다른 스킬과의 경계 명시)

## Hard Rules
## The Build Sequence / Workflow
## Required Output Format
## Tone
```

---

## 4. 14개 스킬 상세

### A. 웹 애니메이션 계열 (6개)

| 스킬 | 역할 | 보조 파일 | 자동발동 |
|---|---|---|---|
| **`emil-design-eng`** | **메인 스킬(674줄)**. 철학 + 애니메이션 결정 프레임워크 + CSS transform/clip-path 마스터리 + 제스처 + 성능 + 접근성 + Sonner 제작 원칙 | — | O |
| **`animate`** | 애니메이션 **신규 제작**. 7단계 순차 결정: ①애니메이션 할까 → ②목적 → ③도구 → ④속성 → ⑤커브/시간 → ⑥중단처리 → ⑦접근성 | `RECIPES.md` (레시피 14종) | O |
| **`review-animations`** | 기존 애니메이션 **감사/리뷰**. "10가지 절대 기준" + 즉시 flag 트리거 14개 + Block/Approve 판정 | `STANDARDS.md` (정확한 수치 카탈로그) | X (수동) |
| **`improve-animations`** | 코드베이스 **전체 감사 → 우선순위 실행계획서 발행**. 비싼 모델이 계획, 싼 모델이 실행 | `AUDIT.md`(8개 감사축) + `PLAN-TEMPLATE.md` | O |
| **`find-animation-opportunities`** | 애니메이션이 **없는데 있어야 할 곳** 탐색. 핵심은 **절제** — "넣지 말아야 할 곳"도 반드시 보고 | — | O |
| **`animation-vocabulary`** | **역방향 용어사전**. "팝오버 열릴 때 통통 튀는 그거" → `Pop in`. 11개 카테고리 글로서리 | — | O |

**`animate/RECIPES.md` 레시피 목록**: 버튼 프레스 / 드롭다운·팝오버·메뉴·셀렉트 / 툴팁 / 모달 / 드로어·시트 / 토스트 / 아코디언 / 그룹 stagger / hold-to-confirm / 탭 인디케이터 색전환 / 스크롤 리빌 / 드래그 dismiss / 크로스페이드 마스킹 / 라이브러리 없는 프로그래매틱

### B. 디자인 품질 / 검증 계열 (3개)

| 스킬 | 역할 | 보조 파일 |
|---|---|---|
| **`break-ui`** | **적대적 테스트**. 최악 데이터(초장문 이름, 안 끊기는 이메일, 1글자 이름, 1,284명, 0개, 이모지, RTL, 200% 줌) 투입 → `Demo/Worst case` 토글 생성 → 깨진 것 전부 리포트. 6단계 워크플로 | `CATALOG.md` (9분야 최악값 카탈로그) |
| **`prototype`** | 한 UI를 **진짜로 다른 방향 3~5개 버전**으로 만들어 비주얼 피커로 비교. 변형끼리 "축(axis)"이 달라야 함 | `PICKER.md` (피커 UI 스펙, 그대로 복붙) |
| **`apple-design`** | Apple WWDC *Designing Fluid Interfaces* 를 **웹용으로 번역**. 17개 섹션: 중단 가능성 / 속도 인계 / 모멘텀 투사 / 러버밴딩 / 재질·깊이 / 타이포그래피 | — |

**`break-ui` 실패 시그니처 예시**

| 증상 | 원인 | 해결 |
|---|---|---|
| 아바타가 타원으로 찌그러짐 | flex 자식이 축소됨 | `flex-shrink: 0` |
| 텍스트가 박스를 넘침 | flex/grid 자식의 `min-width: auto` | `min-width: 0` (grid는 `minmax(0, 1fr)`) |
| 이메일/URL이 화면 밖으로 | 문자열에 줄바꿈 기회가 없음 | `overflow-wrap: anywhere` |
| 우측 액션 버튼이 잘림 | 중간 컨텐츠가 공간 독식 | 중간에 `min-width: 0`, 액션에 `flex-shrink: 0` |

### C. 플랫폼별 계열 (3개)

| 스킬 | 역할 | 보조 파일 |
|---|---|---|
| **`animate-expo`** | React Native / Expo 전용. Reanimated + Gesture Handler + Expo Router + expo-haptics. **JS 스레드 밖으로 모션 내보내기**, 120fps, 햅틱 | `RECIPES.md` (레시피 12종) |
| **`mobile-native`** | 웹앱을 폰에서 **네이티브처럼**. 증상 11개: hover 끈적임 / 탭 회색 플래시 / 100vh 버그 / input 줌 / 300ms 탭 지연 / pull-to-refresh 가로채기 / 노치 safe-area / 롱프레스 텍스트 선택 / 캐러셀 세로 스크롤 / 상태바 색 / "크롬에선 맞는데 폰에선 틀림" | — |
| **`write-swift`** | 모던 Swift 6.3/6.4. 값 타입 모델링 / Swift 6 데이터레이스 안전 / `@concurrent` / 구조적 동시성 / `some` vs `any` / ARC / Swift Testing / 매크로 / 6 마이그레이션 | — |

### D. 선택 / 가이드 계열 (2개)

| 스킬 | 역할 | 보조 파일 |
|---|---|---|
| **`pick-ui-library`** | **큐레이션된 라이브러리만** 추천. 메뉴 나열 금지, 하나만 지목 | — |
| **`ask-sonner`** | Sonner 토스트 라이브러리 **저자 직접 가이드**. 셋업 / 호출 선택 / 레시피 / 스타일링 사다리 / 트러블슈팅 | `API.md` (prop 전체 표) |

**`pick-ui-library` 큐레이션 목록 (전체)**

| 용도 | 라이브러리 |
|---|---|
| 접근성 UI 프리미티브 (dialog, popover, menu, select) | [base-ui](https://base-ui.com) |
| 커맨드 메뉴 (Cmd+K 팔레트) | [cmdk](https://cmdk.paco.me) |
| 토스트 / 알림 | [Sonner](https://sonner.emilkowal.ski) |
| OTP / 인증번호 입력 | [input-otp](https://input-otp.rodz.dev) |
| 컨트롤 패널 / GUI | [Leva](https://github.com/pmndrs/leva), [dialkit](https://joshpuckett.me/dialkit) |
| 범용 애니메이션 (spring, layout, enter/exit) | [motion](https://motion.dev) |
| 숫자 애니메이션 (카운터, 가격) | [NumberFlow](https://number-flow.barvian.me) |
| 애니메이션 텍스트 | [torph](https://torph.lochie.me/) |
| 3D 지구본 | [Cobe](https://cobe.vercel.app) |
| 동적 OG 이미지 | [Satori](https://github.com/vercel/satori) |
| 신택스 하이라이팅 | [shiki](https://shiki.style) |
| 실시간/스트리밍 차트 | [Liveline](https://github.com/benjitaylor/liveline) |
| 일반 차트 | [recharts](https://recharts.org) |
| 드래그 앤 드롭 | [dnd kit](https://dndkit.com) |
| 가상화 (긴 리스트/큰 테이블) | [Virtuoso](https://virtuoso.dev) |
| 상태 관리 | [zustand](https://zustand.docs.pmnd.rs) |
| 조건부 className | [clsx](https://github.com/lukeed/clsx) |
| 타입 안전 variant 스타일링 | [cva](https://cva.style) |
| 테마 전환 / 다크모드 | [next-themes](https://github.com/pacocoursey/next-themes) |

---

## 5. 설계상 뛰어난 점

### 5.1 Progressive Disclosure (점진적 공개)

```
SKILL.md        (109줄, 항상 로드)   ← 판단 로직만
  └─ AUDIT.md   (115줄, 필요시만)    ← 상세 수치
  └─ RECIPES.md (324줄, 필요시만)    ← 구현 코드
```

→ 컨텍스트 토큰 **대폭 절감**. 내 에이전트에 그대로 적용 가능.

### 5.2 역할 경계 명시 (충돌 방지)

> "It does ONE thing: turn a request for motion into an implementation.
> It does not audit a codebase (that's `improve-animations`),
> critique a diff (that's `review-animations`),
> hunt for places that could animate (that's `find-animation-opportunities`),
> or build for React Native (that's `animate-expo`)."

→ 멀티 에이전트에서 역할 중복 방지의 정석.

### 5.3 모델 티어링 (비용 최적화)

`improve-animations`의 전략:
> "비싼 모델로 **판단/계획**만 → 싼 모델이 **실행**"

→ Opus가 계획서 쓰고 Haiku가 100개 파일 수정. 비용 대폭 절감.

### 5.4 출력 포맷 강제 (+ 틀린 예시 제시)

```markdown
## Review Format (Required)
반드시 Before/After 컬럼이 있는 마크다운 표를 쓸 것.
리스트 금지.

Wrong format (never do this):
  Before: transition: all 300ms
  After:  transition: transform 200ms ease-out
```

→ **틀린 예시까지 보여주는** 게 포인트. 파싱 가능한 출력 보장.

### 5.5 게이트 우선 설계

```
Step 1: 애니메이션 해야 하나?  ← "No"면 즉시 종료
Step 2: 목적이 뭐야?           ← 못 대면 즉시 종료
Step 3~7: ...
```

> "The gate below exists to produce zero lines of code sometimes.
> That's a success, not a dodge."

→ 과잉 생성 문제의 해법.

### 5.6 `disable-model-invocation: true`

`review-animations`, `prototype`, `pick-ui-library` 3개는 **명시적 호출 전용**.
AI가 멋대로 끼어들지 않음.

---

## 6. 핵심 규칙 요약

### 6.1 이징 커브 (기본 CSS 이징은 너무 약해서 사용 금지)

```css
--ease-out:    cubic-bezier(0.23, 1, 0.32, 1);     /* UI 진입/퇴장 */
--ease-in-out: cubic-bezier(0.77, 0, 0.175, 1);    /* 화면 내 이동 */
--ease-drawer: cubic-bezier(0.32, 0.72, 0, 1);     /* iOS 드로어 (Ionic) */
```

커브가 더 필요하면 [easing.dev](https://easing.dev/) / [easings.co](https://easings.co/) 에서 가져옴. 직접 만들지 말 것.

### 6.2 이징 선택 결정표

| 상황 | 이징 |
|---|---|
| 진입/퇴장 | `ease-out` |
| 화면 내 이동/모핑 | `ease-in-out` |
| 호버/색 변화 | `ease` |
| 등속 운동 (마퀴, 프로그레스) | `linear` |
| 기본값 | `ease-out` |

**`ease-in`은 UI에서 절대 금지.** 시작이 느려서 사용자가 가장 주의 깊게 보는 순간을 지연시킴. `ease-out` 200ms가 `ease-in` 200ms보다 *체감상* 빠름.

### 6.3 빈도 기반 결정표 (가장 중요)

| 사용 빈도 | 결정 |
|---|---|
| 하루 100회+ (키보드 단축키, 커맨드 팔레트) | **애니메이션 절대 금지** |
| 하루 수십 회 (호버, 리스트 내비게이션) | 제거 또는 극도로 축소 |
| 간헐적 (모달, 드로어, 토스트) | 표준 애니메이션 |
| 드묾/최초 1회 (온보딩, 축하) | 즐거움(delight) 허용 |

> Raycast는 열고 닫을 때 애니메이션이 없음 — 하루 수백 번 쓰는 것엔 그게 정답.

### 6.4 지속시간 예산

| 요소 | 시간 |
|---|---|
| 버튼 프레스 피드백 | 100~160ms |
| 툴팁, 작은 팝오버 | 125~200ms |
| 드롭다운, 셀렉트 | 150~250ms |
| 모달, 드로어 | 200~500ms |
| 마케팅/설명용 | 더 길어도 됨 |

**규칙: UI 애니메이션은 300ms 미만.**

### 6.5 애니메이션 목적 (하나는 반드시 대야 함)

- **Feedback** — 인터페이스가 사용자를 들었다는 확인
- **Spatial consistency** — 어디서 왔고 어디로 갔는지
- **State indication** — 상태 변화를 읽히게
- **Preventing a jarring change** — 텔레포트 방지
- **Explanation** — 작동 방식 설명 (마케팅/온보딩 한정)
- **Delight** — 드묾/최초 1회 티어에서만 허용

목적을 못 대면 만들지 않음. "멋있어서"는 사유가 안 됨.

### 6.6 10가지 절대 기준 (`review-animations`)

1. **Justified motion** — 목적 없는 애니메이션은 Block
2. **Frequency-appropriate** — 키보드/100회+는 애니메이션 없음
3. **Responsive easing** — 진입/퇴장은 `ease-out`. `ease-in`은 Block
4. **Sub-300ms UI** — 300ms 초과는 사유 필요
5. **Origin & physical correctness** — 팝오버는 트리거에서 자라남, `scale(0)` 금지 (모달은 중앙 예외)
6. **Interruptibility** — 빠르게 트리거되는 모션은 중단 가능해야 함 (keyframes 금지, transition/spring 사용)
7. **GPU-only properties** — `transform`과 `opacity`만. `width`/`height`/`margin`/`padding`/`top`/`left` 금지
8. **Accessibility** — `prefers-reduced-motion` 준수(0이 아니라 완화), hover는 `@media (hover: hover) and (pointer: fine)` 게이팅
9. **Asymmetric enter/exit** — 의도적 동작은 느리게, 시스템 응답은 빠르게
10. **Cohesion** — 컴포넌트 성격과 모션이 일치

### 6.7 즉시 flag 하는 트리거 14개

- `transition: all`
- `scale(0)` 또는 초기 transform 없는 순수 페이드 진입
- UI에 `ease-in`
- 키보드 단축키 / 커맨드 팔레트 / 100회+ 동작에 애니메이션
- 사유 없는 300ms 초과
- 트리거에 붙은 팝오버에 `transform-origin: center`
- 토스트/토글 등 빠르게 추가되는 것에 keyframes
- 레이아웃 속성 애니메이션
- 페이지가 바쁠 때 돌아가는 Framer Motion `x`/`y`/`scale`
- 부모의 CSS 변수로 자식 transform 구동 (style recalc 폭풍)
- 움직임에 `prefers-reduced-motion` 미처리
- 게이팅 없는 `:hover` 모션
- press-and-release / hold 상호작용에 대칭 타이밍
- 30~80ms stagger가 맞는데 전부 한꺼번에 등장

### 6.8 수정 선호 위계 (앞쪽을 먼저)

1. **애니메이션 삭제** (고빈도 / 목적 없음 / 키보드 트리거)
2. **축소** (짧게, 작게, 속성 줄이기)
3. **이징 수정** (`ease-in` → `ease-out` / 강한 커브)
4. **origin/물리성 수정** (`scale(0)` → `scale(0.95)` + opacity)
5. **중단 가능하게** (keyframes → transition, 제스처는 spring)
6. **GPU로 이동** (레이아웃 속성 → transform/opacity, 축약형 → 전체 transform 문자열, WAAPI)
7. **비대칭 타이밍**
8. **폴리시** (blur 마스킹, stagger, `@starting-style`, spring)
9. **접근성 & 응집성**

### 6.9 성능 치트시트

| 문제 | 해결 |
|---|---|
| 애니메이션 끊김 | `transform`/`opacity` 사용, `width`/`top` 금지 |
| 긴 리스트 스크롤 느림 | 가상화 (보이는 것만 렌더) |
| blur 성능 문제 | 애니메이션 `blur()`는 20px 이하 |
| Motion의 `x`/`y`가 프레임 드랍 | 전체 `transform` 문자열로 |
| 엉뚱한 속성이 애니메이션됨 | `transition: all` 금지, 속성 명시 |
| React가 매 프레임 리렌더 | state 대신 `ref.current.style`에 직접 쓰기 |
| 모션 시작 시 1px 이동 | `will-change: transform` (증상 보일 때만) |

### 6.10 Framer Motion GPU 가속 함정 (중요)

```jsx
<motion.div animate={{ x: 100 }} />                          // 부하 시 프레임 드랍
<motion.div animate={{ transform: "translateX(100px)" }} />  // 하드웨어 가속
```

축약형(`x`, `y`, `scale`)은 `requestAnimationFrame` 메인 스레드에서 돌아서 **GPU 가속이 안 됨**.
Vercel 대시보드 탭 애니메이션이 페이지 로드 중 프레임을 떨궜고, CSS 애니메이션으로 바꿔서 해결한 실제 사례.

### 6.11 제스처: 속도 기반 dismiss (Sonner 실제 코드)

```js
const timeTaken = new Date().getTime() - dragStartTime.current.getTime();
const velocity = Math.abs(swipeAmount) / timeTaken;

if (Math.abs(swipeAmount) >= SWIPE_THRESHOLD || velocity > 0.11) {
  dismiss();
}
```

거리 임계값을 넘지 않아도 **빠르게 튕기면(velocity > 0.11)** dismiss. 임계값만 쓰면 뻣뻣하게 느껴짐.

### 6.12 Sonner 원칙 (사랑받는 컴포넌트 만들기)

1. **개발자 경험이 핵심** — 훅/컨텍스트/복잡한 셋업 없음. `<Toaster />` 한 번 넣고 어디서든 `toast()`
2. **옵션보다 좋은 기본값** — 대부분 커스터마이즈 안 함. 기본이 훌륭해야 함
3. **이름이 정체성을 만듦** — "Sonner"(프랑스어 '울리다')가 "react-toast"보다 우아함
4. **엣지 케이스를 보이지 않게 처리** — 탭 숨겨지면 타이머 정지, 스택 사이 갭을 pseudo-element로 메워 hover 유지, 드래그 중 포인터 캡처
5. **동적 UI엔 keyframes 대신 transition** — 중단 시 keyframes는 0부터 재시작
6. **훌륭한 문서 사이트** — 만져보고 이해한 뒤 쓰게 함

---

## 7. 나에게 주는 도움

| 문제 | 이 스킬이 해주는 것 |
|---|---|
| AI가 짠 UI가 "뭔가 싸구려 같다" | 그 '뭔가'의 정체를 **명시적 체크 항목으로 분해** |
| 애니메이션 숫자를 매번 감으로 찍음 | **표에서 바로 꺼내 씀** (근거까지) |
| 데모 데이터로만 테스트해서 배포 후 터짐 | `break-ui`가 **배포 전에 터뜨려줌** |
| 어떤 라이브러리 쓸지 매번 검색 | **검증된 19개 리스트**에서 즉결 |
| 디자인 리뷰해줄 시니어가 없음 | **Vercel/Linear 시니어 리뷰를 상시 호출** |
| AI 에이전트 만드는 법을 배우고 싶음 | **잘 만든 Skill 설계의 교과서** (숨은 최대 가치) |

### Before / After 실제 비교

**Before (스킬 없음)**

```css
transition: all 0.4s ease-in;
transform: scale(0);
```

**After (스킬 있음)**

```css
/* 모달은 '간헐적' 빈도 → 표준 애니메이션 OK
   목적: '급작스런 변화 방지' / 진입이므로 ease-out, 220ms */
transition: transform 220ms cubic-bezier(0.23, 1, 0.32, 1),
            opacity   220ms cubic-bezier(0.23, 1, 0.32, 1);
transform: scale(0.95);   /* scale(0) 아님 */
opacity: 0;
transform-origin: center; /* 모달은 예외적으로 중앙 유지 */
```

차이는 숫자 몇 개. 그 숫자를 아는 게 10년 경력이고, 그 10년을 파일로 압축한 것.

---

## 8. Q&A 7문 7답

### Q1. 설치 및 사용법?

**방법 A — 공식 CLI (가장 쉬움)**

```bash
npx skills@latest add emilkowalski/skills
# 내 포크 버전
npx skills@latest add bmshin94/emilkowalski-skills
```

**방법 B — 수동 복사**

```bash
# 전역 설치 (모든 프로젝트)
mkdir -p ~/.claude/skills && cp -r skills/* ~/.claude/skills/

# 프로젝트 전용 (팀 공유 가능, git 커밋됨)
mkdir -p .claude/skills && cp -r skills/* .claude/skills/
```

최종 구조:

```
~/.claude/skills/
├── animate/
│   ├── SKILL.md      ← 이 파일명이어야 인식됨
│   └── RECIPES.md
└── emil-design-eng/
    └── SKILL.md
```

**방법 C — 다른 AI 도구**

| 도구 | 방법 |
|---|---|
| Cursor | `.cursor/rules/`에 `.mdc`로 변환 |
| Gemini CLI | 루트 `GEMINI.md`에 내용 합치기 |
| Windsurf | `.windsurfrules` |
| 일반 챗봇 | `SKILL.md` 내용 복붙 |

**사용법**

```bash
# 명시적 호출
/review-animations
/prototype 가격 카드
/pick-ui-library 드래그앤드롭 필요해
/break-ui MemberList 컴포넌트

# 자동 발동 — 자연어로 말하면 AI가 description 보고 알아서 켬
"이 버튼 호버 애니메이션 넣어줘"         → animate
"폰에서 탭할 때 회색 번쩍이는 거 고쳐줘"  → mobile-native
```

`review-animations`, `prototype`, `pick-ui-library`는 `disable-model-invocation: true` → **슬래시로만** 켜짐.

**확인**: `ls ~/.claude/skills/` 로 14개 폴더 확인. Claude Code에서 `/` 입력 시 목록에 나와야 함. 안 보이면 세션 재시작.

---

### Q2. 플러그인? 스킬? MCP?

**100% 스킬(Skill)이다.** 전수조사 증거: `.json` / `.yaml` / `.toml` 매니페스트 0개.

| 구분 | 특징 | 이 저장소 |
|---|---|---|
| **Skill** | `SKILL.md` + YAML frontmatter. 마크다운만. AI가 **읽는 지식** | **O** |
| **Plugin** | `.claude-plugin/plugin.json` 필요. 스킬+커맨드+훅+에이전트 묶음 배포 | X |
| **MCP** | 서버 프로세스. stdio/HTTP. **실행되는 도구** 제공 | X |

```
Skill  = AI한테 "이렇게 해" 라고 가르치는 책   (지식)
Plugin = 책 + 도구 + 자동화를 한 박스에 포장   (패키징)
MCP    = AI에게 새로운 손을 달아주는 서버      (능력)
```

> 실전 팁: 이 14개 스킬에 `plugin.json` 하나만 추가하면 **플러그인으로 재포장** 가능 → 팀 전체에 한 줄로 배포. (수익화 아이디어 중 하나)

---

### Q3. API 토큰 필요?

**이 저장소 자체는 전혀 필요 없음.**

| 대상 | 토큰 | 비용 |
|---|---|---|
| 이 스킬 저장소 | 불필요 | **완전 무료** (마크다운일 뿐) |
| `npx skills@latest add` | 불필요 | 무료 (공개 GitHub에서 복사) |
| **Claude Code 본체** | **필요** | Pro/Max 구독 로그인 **또는** Anthropic API 키 |
| 추천 라이브러리 (motion, Sonner, zustand…) | 불필요 | 오픈소스 무료 |
| `aiforui.dev` 뉴스레터 | 불필요 | 무료 |

정리: 스킬은 공짜. 단 스킬을 읽어줄 **AI 구독/API 키는 이미 있어야** 함 → 현재 사용 중이므로 추가 비용 0원.

---

### Q4. AI 에이전트 구축에 도움될까?

**방향 A — 간접 활용 (바로 가능): 에이전트의 UI 품질 보증기**

```
사용자 요청
   ↓
[생성 에이전트]  animate 스킬 로드 → UI 코드 생성
   ↓
[검증 에이전트]  review-animations 로드 → Block/Approve 판정
   ↓                    ↓ Block이면 루프백
[적대 에이전트]  break-ui 로드 → 최악 데이터로 터뜨림
   ↓
배포
```

**방향 B — 직접 활용 (진짜 가치): 에이전트 설계 교과서**

[5. 설계상 뛰어난 점](#5-설계상-뛰어난-점) 의 5가지 패턴을 그대로 차용:
Progressive Disclosure / 역할 경계 명시 / 모델 티어링 / 출력 포맷 강제 / 게이트 우선 설계

**종합 평가**

| 용도 | 점수 |
|---|---|
| UI 생성 에이전트 품질 향상 | ★★★★★ |
| 에이전트 설계 학습 교재 | ★★★★★ |
| 백엔드/데이터 에이전트 | ★ (무관) |
| 에이전트 "실행 능력" 추가 | X (MCP 영역) |

---

### Q5. 수익화 아이디어 있어?

→ [9. 수익화 아이디어 7가지](#9-수익화-아이디어-7가지) 참조.

TOP 3 미리보기:
1. "AI 코딩 시대의 UI 품질" 한국어 강의
2. 업종별 스킬팩 제작·판매 (특히 **한국형 UI 팩**)
3. SaaS: UI 자동 감사 봇 (GitHub App)

---

### Q6. React나 PHP로 만들 수 있어?

**이 저장소 자체는 만들 게 없다** (마크다운 22개). 하지만 **이걸 활용하는 제품**은 완전 가능.

**React로 만들 수 있는 것**

| 제품 | 설명 | 난이도 |
|---|---|---|
| 스킬 브라우저 웹앱 | 14개 스킬 검색/필터/태그 탐색, 코드 복사 | ★★ |
| **인터랙티브 애니메이션 플레이그라운드** | 이징/duration 슬라이더로 실시간 체감. `ease-in` vs `ease-out` 나란히 비교 → 교육 효과 극대 | ★★★ |
| Before/After 쇼케이스 | `scale(0)` vs `scale(0.95)` 토글 갤러리 | ★★ |
| 스킬 빌더 (SaaS) | 폼 채우면 `SKILL.md` 생성 + zip 다운로드 | ★★★ |
| UI 감사 대시보드 | 저장소 연결 → 위반 사항 시각화 | ★★★★ |
| break-ui 데이터 생성기 | `CATALOG.md` 기반 최악 fixture 생성기 | ★★ |

```jsx
// 플레이그라운드 핵심 코드
const CURVES = {
  'ease-in (금지)':  'cubic-bezier(0.42, 0, 1, 1)',
  'ease-out (기본)': 'cubic-bezier(0.23, 1, 0.32, 1)',
  'drawer (iOS)':    'cubic-bezier(0.32, 0.72, 0, 1)',
};

function EasingLab() {
  const [curve, setCurve] = useState('ease-out (기본)');
  const [ms, setMs] = useState(200);
  const [open, setOpen] = useState(false);

  return (
    <>
      <select value={curve} onChange={e => setCurve(e.target.value)}>
        {Object.keys(CURVES).map(k => <option key={k}>{k}</option>)}
      </select>
      <input type="range" min={80} max={600} value={ms}
             onChange={e => setMs(+e.target.value)} />
      <span>{ms}ms</span>
      <button onClick={() => setOpen(o => !o)}>토글</button>

      <div style={{
        transition: `transform ${ms}ms ${CURVES[curve]}, opacity ${ms}ms ${CURVES[curve]}`,
        transform: open ? 'scale(1)' : 'scale(0.95)',   // scale(0) 아님
        opacity:   open ? 1 : 0,
        transformOrigin: 'top left',                     // 트리거 기준
      }}>드롭다운 내용</div>
    </>
  );
}
```

**PHP로 만들 수 있는 것**

| 제품 | 설명 |
|---|---|
| 스킬 마켓플레이스 백엔드 | Laravel + MySQL. 업로드/결제/다운로드/버전관리 |
| 결제·구독 시스템 | Laravel Cashier + 토스페이먼츠/아임포트 |
| WordPress 플러그인 | 블로그에 애니메이션 가이드 위젯 삽입 |
| Git 웹훅 수신 서버 | PR 이벤트 받아 AI API 호출 → 리뷰 코멘트 |
| CMS (한국어 번역판) | 스킬 한글 번역 버전 관리·배포 |

```php
<?php
// Laravel — 스킬 마켓플레이스 결제 라우트
Route::post('/skills/{slug}/purchase', function (Request $r, string $slug) {
    $skill = Skill::where('slug', $slug)->firstOrFail();
    $order = $r->user()->orders()->create([
        'skill_id' => $skill->id,
        'amount'   => $skill->price,
        'status'   => 'pending',
    ]);
    // 토스페이먼츠 결제창 생성 → 성공 시 zip 다운로드 토큰 발급
    return response()->json(['orderId' => $order->id]);
});
```

**추천 스택**

```
프론트: Next.js + TypeScript + motion + Tailwind + Sonner
        (스킬이 추천한 라이브러리를 그대로 써서 "자기 증명")
백엔드: Laravel 또는 Next.js API Routes
결제:   토스페이먼츠 / 아임포트
배포:   Vercel (프론트) + Forge/Cloudtype (Laravel)
```

> 킬러 포인트: "애니메이션 가이드 사이트인데 애니메이션이 구리다"면 설득력 제로.
> 이 프로젝트만큼은 **스킬 규칙을 100% 지켜서** 만들어야 함. 그게 최고의 포트폴리오.

---

### Q7. 유튜브 강의 영상 제작 가능할까?

**법적 체크 (MIT License)**

```
Copyright (c) 2026 Emil Kowalski
"Permission is hereby granted, free of charge, to any person...
 to use, copy, modify, merge, publish, distribute, sublicense,
 and/or SELL copies of the Software"
```

| 항목 | 가능 |
|---|---|
| 영상에서 내용 소개/설명 | O |
| 코드 조각 화면 표시 | O |
| 수익화 (광고/멤버십/유료강의) | O (명시적 허용) |
| 번역해서 배포 | O |
| 출처 표기 | **필수 매너** — 설명란에 원저작자 + MIT + 저장소 링크 |

> 법적으로는 되지만, **"원작자 Emil Kowalski의 저장소를 한국어로 해설합니다"** 명시 + 원본 링크 게시가 맞음. 채널 신뢰도에도 유리. 저작권 통째 복붙 강의로 판매하면 평판 리스크.

**추천 커리큘럼 (12부작)**

| # | 제목 | 길이 | 훅 |
|---|---|---|---|
| 0 | 【예고】AI가 짠 UI가 싸구려로 보이는 이유 | 1분 | Shorts 바이럴용 |
| 1 | AI는 `ease-in`을 쓴다. 왜 틀렸나 | 10분 | 나란히 비교 데모 |
| 2 | Raycast는 왜 애니메이션이 없을까 — 빈도의 법칙 | 12분 | 반직관적 = 클릭률 상승 |
| 3 | `scale(0)` 금지: 무에서 나타나는 건 없다 | 8분 | 눈에 바로 보임 |
| 4 | 300ms의 법칙 + 체감 성능의 과학 | 12분 | 스피너 속도 실험 |
| 5 | Framer Motion `x`/`y`가 프레임을 떨구는 진짜 이유 | 15분 | DevTools 실측 |
| 6 | `clip-path`로 만드는 Hold-to-delete 버튼 | 18분 | 만들기 재미 |
| 7 | Sonner 소스로 배우는 제스처: velocity 0.11의 비밀 | 20분 | 1,300만 다운로드 코드 해부 |
| 8 | 폰에서만 이상한 11가지 (100vh, 탭 지연, 노치) | 16분 | 검색량 최상위 |
| 9 | 최악 데이터로 내 UI 터뜨리기 (break-ui) | 14분 | 터지는 장면 쾌감 |
| 10 | Claude Code 스킬 직접 만들기 | 20분 | 실무 적용 |
| 11 | 멀티 에이전트 UI 품질 파이프라인 구축 | 25분 | 유료 강의 전환 유도 |

**제작 포인트**

| 요소 | 전략 |
|---|---|
| 핵심 무기 | 반드시 **Before/After 나란히 재생** |
| 슬로모션 | 0.2배속. 스킬 자체가 `## Debugging`에서 추천하는 방법 |
| 화면 녹화 | Chrome DevTools → Animations 패널 (프레임별) |
| 썸네일 | 좌 ❌ 빨간 테두리 / 우 ⭕ 초록 테두리 비교형 |
| Shorts 전략 | 규칙 1개 = Shorts 1개. 14개 스킬 → 60개+ 양산 |
| 차별점 | 한국어 + AI 시대 맥락 = 경쟁 거의 없음 |
| 수익 경로 | 애드센스 → 멤버십 → 유료 강의/스킬팩 |

**성공 확률**

| 지표 | 평가 |
|---|---|
| 시각적 임팩트 | ★★★★★ (애니메이션 = 영상에 최적) |
| 한국어 경쟁 | ★★★★★ (거의 없음) |
| 검색 수요 | ★★★★ (AI 코딩 + UI 품질 상승세) |
| 제작 난이도 | ★★★ (데모 코드 품이 듦) |
| 수익 전환성 | ★★★★★ (B2B 강의 확장 용이) |

---

## 9. 수익화 아이디어 7가지

> 전제: **스킬 파일 자체를 팔긴 어렵다** (MIT 무료 공개 → 누구나 가져감).
> 돈은 **"스킬 주변"** 에서 나온다.

### 모델 1. 한국어 교육 콘텐츠 → 유료 강의 (가장 현실적)

**왜 1번인가**: 진입 장벽 제로 / MIT라 법적 리스크 없음 / 한국어 경쟁자 거의 없음 / 유튜브→강의 퍼널은 검증된 모델

| 단계 | 상품 | 가격 | 월 예상 |
|---|---|---|---|
| 1 | 유튜브 무료 (애드센스) | — | 10~50만원 |
| 2 | 멤버십 (조기 공개 + 코드) | 월 9,900원 | 50명 → 50만원 |
| 3 | **유료 VOD 강의** | 129,000원 | 20명 → 258만원 |
| 4 | **기업 사내 교육** | 회당 150~300만원 | 월 1회 → 200만원 |
| 5 | 1:1 UI 코드 리뷰 | 시간당 10만원 | 월 10시간 → 100만원 |

**포지셔닝 (핵심)**

```
X  "애니메이션 강의"                      → 경쟁 많음, 단가 낮음
O  "AI가 짠 코드의 품질을 판별하는 능력"   → 경쟁 없음, 단가 높음
```

모두가 AI로 코드를 뽑는데, **뽑힌 코드가 좋은지 판별할 사람이 없다.** 그 공백이 시장.

**로드맵**

```
1~2개월: 유튜브 12편 + Shorts 40개 (구독자 1,000 목표)
3개월:   멤버십 오픈 + 무료 PDF 체크리스트로 이메일 수집
4~5개월: VOD 강의 제작 (인프런/클래스101/자체 판매)
6개월~:  기업 교육 영업 (판교/강남 스타트업)
```

---

### 모델 2. 업종별 "스킬팩" 제작·판매

Emil 스킬은 **범용 웹 UI**용. **업종 특화는 아무도 안 만들었다.**

| 스킬팩 | 내용 | 가격 |
|---|---|---|
| 이커머스 UI 팩 | 장바구니 애니메이션, 결제 퍼널, 재고 0 상태, 할인 배지, 리뷰 별점, 무한스크롤 | $49 |
| 대시보드/어드민 팩 | 데이터 테이블(1만 행), 차트 전환, 필터 칩, 빈 상태, 로딩 스켈레톤 | $59 |
| 핀테크/뱅킹 팩 | 금액 표기 규칙, 숫자 애니메이션 금지 규칙, 보안 입력, 거래 내역 | $79 |
| 의료/공공 팩 | WCAG AAA 접근성, 고령자 대응, 폰트 크기, 고대비 | $89 |
| **한국형 UI 팩** | 본인인증 플로우, 토스페이먼츠, 카카오 로그인, 다음 주소검색, 사업자번호 검증, **한글 줄바꿈 `word-break: keep-all`**, 성인인증 | $69 |

> **한국형 팩이 진짜 블루오션.** `word-break: keep-all` 하나만 해도 외국 스킬엔 절대 없다. 국내 개발자 전원이 겪는 문제인데 문서화된 적 없음.

**수익 모델**

| 방식 | 예상 |
|---|---|
| 개별 판매 (Gumroad/Lemon Squeezy) | $49 × 20건 = $980/월 |
| 번들 전체 | $199 × 5건 = $995/월 |
| 팀 라이선스 (5석) | $499 × 2건 = $998/월 |
| 월 구독 (업데이트 포함) | $19 × 50명 = $950/월 |
| | **합계 약 $3,900/월 (약 540만원)** |

**제작 구조** (Emil의 구조 차용, MIT라 합법)

```
my-ecommerce-pack/
├── skills/
│   ├── cart-animation/
│   │   ├── SKILL.md      ← 판단 로직
│   │   └── RECIPES.md    ← 구현 코드
│   ├── checkout-funnel/
│   └── korean-text/      ← keep-all, 조사 처리 등
├── .claude-plugin/
│   └── plugin.json       ← 플러그인으로 포장 (한 줄 설치)
├── LICENSE               ← 상업 라이선스
└── README.md
```

---

### 모델 3. SaaS — UI 자동 감사 봇 (수익 상한 최고)

`review-animations` + `break-ui`를 **GitHub App**으로 자동화.

```
개발자가 PR 올림
      ↓
GitHub Webhook → 서버 (Laravel/Next.js)
      ↓
변경된 CSS/TSX diff 추출
      ↓
Claude API 호출 (프롬프트 = review-animations SKILL.md)
      ↓
PR에 자동 코멘트:
  | Before | After | Why |
  |---|---|---|
  | transition: all 300ms | transition: transform 200ms ease-out | ... |
  Block: ease-in on dropdown (src/Menu.tsx:34)
```

| 플랜 | 가격 | 내용 |
|---|---|---|
| Free | $0 | 공개 저장소, 월 50 PR |
| Pro | $19/월 | 비공개 저장소, 무제한 |
| Team | $99/월 | 5 저장소, 커스텀 규칙 |
| Enterprise | $499/월 | 자체 호스팅, 디자인 시스템 연동 |

100 Pro + 20 Team + 2 Ent = $1,900 + $1,980 + $998 = **약 $4,878/월 (약 680만원)**

**기술 스택**

```
GitHub App: Probot (Node) 또는 Laravel + Webhook
AI:         Claude API (claude-sonnet-5-5 — 가성비)
DB:         PostgreSQL (사용량 추적)
결제:       Stripe / 토스페이먼츠
프론트:     Next.js 대시보드
```

**리스크**: Claude API 원가 관리 필수 (diff 크기 제한, 프롬프트 캐싱). 경쟁자 등장 가능 → 한국어 리뷰 + 국내 결제로 차별화.

---

### 모델 4. 인터랙티브 플레이그라운드 (프리미엄 기능)

| 무료 | 유료 ($9/월) |
|---|---|
| 이징 커브 비교 | 커브 저장 & 공유 |
| duration 슬라이더 | 팀 프리셋 라이브러리 |
| 레시피 5개 | 레시피 전체 50개 |
| 코드 복사 | Figma 플러그인 연동 |
| — | CSS 변수 자동 생성/내보내기 |

```
구독 300명 × $9 = $2,700/월 (약 380만원)
+ 스폰서 배너 (라이브러리 회사) $500/월
```

**보너스**: 유튜브 영상 소재가 무한 생성됨. 영상 → 사이트 유입 → 구독 전환 선순환.

---

### 모델 5. 한국어 번역판 + 로컬라이징 (가장 빠름)

스킬은 전부 영어. AI는 한국어 프롬프트에 한국어 스킬을 더 잘 매칭하고, **사람이 읽고 배우려면** 한국어가 압도적.

| 상품 | 가격 |
|---|---|
| 번역본 무료 공개 (GitHub) | $0 → 트래픽/권위 확보용 |
| 한국어 PDF 전자책 | 19,000원 |
| 노션 템플릿 (체크리스트) | 29,000원 |
| 인쇄 포스터 (이징 커브 차트) | 15,000원 |
| 한국형 보강판 (keep-all 등 추가) | 49,000원 |

**실행 기간: 1~2주** (가장 빠른 현금화)

법적: MIT라 번역·판매 OK. `LICENSE` 원문 포함 + 원저작자 표기 필수.

---

### 모델 6. 컨설팅 / 수탁 개발 (단가 최고)

| 상품 | 가격 |
|---|---|
| UI 품질 감사 리포트 (1 제품) | 300~500만원 |
| 디자인 시스템 모션 토큰 구축 | 800~1,500만원 |
| 사내 AI 스킬팩 구축 (고객사 전용) | 1,000~2,000만원 |
| 리테이너 (월 리뷰 계약) | 월 200~400만원 |

**영업 포인트**

> "AI로 개발 속도는 3배 올랐는데, **UI 품질 기준이 없어서** 제품이 싸구려로 보입니다.
> 저희가 귀사 전용 AI 스킬팩을 만들어 **모든 개발자가 자동으로 같은 품질 기준**을 지키게 합니다."

**타겟**: 시리즈 A~C 스타트업, SI 업체, 금융권 디지털 부서

---

### 모델 7. 스킬 마켓플레이스 플랫폼 (최대 야망)

```
판매자: 스킬팩 업로드 → 가격 설정
구매자: 검색 → 결제 → 원클릭 설치
플랫폼: 거래액 20~30% 수수료
```

**기능**: 스킬 검색/카테고리/리뷰 / 버전 관리 + 자동 업데이트 / `npx` 원클릭 설치 CLI / 팀 라이선스 관리 / 판매자 정산 대시보드

```
GMV 월 5,000만원 × 수수료 25% = 1,250만원/월
+ 프리미엄 입점비 + 추천 노출 광고
```

**현실 체크**: 난이도 최상. 먼저 모델 1·2로 신뢰와 자본을 쌓고 나중에 갈 길.

---

### 7개 모델 총정리

| # | 모델 | 초기투자 | 소요시간 | 월 수익 잠재 | 난이도 | 추천 순서 |
|---|---|---|---|---|---|---|
| 5 | 한국어 번역판 | 0원 | 1~2주 | 50~200만 | ★ | **1 (지금 당장)** |
| 1 | 유튜브 → 강의 | 0원 | 3~6개월 | 100~600만 | ★★ | **2 (동시 시작)** |
| 2 | 업종별 스킬팩 | 0원 | 1~2개월 | 200~500만 | ★★ | **3 (한국형 팩부터)** |
| 6 | 컨설팅 | 0원 | 신뢰 쌓인 후 | 300~1,500만 | ★★★ | 4 |
| 4 | 플레이그라운드 | 서버비 | 2~3개월 | 200~400만 | ★★★ | 5 |
| 3 | SaaS 감사 봇 | API비 | 3~6개월 | 300~700만 | ★★★★ | 6 |
| 7 | 마켓플레이스 | 큼 | 6~12개월 | 1,000만+ | ★★★★★ | 7 |

---

## 10. 실행 로드맵

```
┌─────────────────────────────────────────────────────┐
│ 1단계 (1개월) — 씨앗 뿌리기                           │
│   ① 한국어 번역 GitHub 공개 (무료) → 권위 확보        │
│   ② 유튜브 Shorts 10개 (규칙 1개 = 1개)              │
│   ③ 무료 PDF 체크리스트 → 이메일 수집 시작            │
│                                                     │
│ 2단계 (2~3개월) — 첫 수익                             │
│   ④ 유튜브 롱폼 12편 업로드                           │
│   ⑤ 한국형 UI 스킬팩 판매 ($69)                       │
│   ⑥ 플레이그라운드 MVP (영상 소재 + 유입)             │
│                                                     │
│ 3단계 (4~6개월) — 본격 매출                           │
│   ⑦ 유료 VOD 강의 출시 (129,000원)                   │
│   ⑧ 기업 교육 영업 시작                               │
│   ⑨ 업종별 스킬팩 3종 확장                            │
│                                                     │
│ 4단계 (6개월+) — 스케일                               │
│   ⑩ SaaS 감사 봇 또는 컨설팅 사업화                   │
└─────────────────────────────────────────────────────┘
```

### 가장 중요한 한 가지

> **"AI가 코드를 쓰는 시대에, 품질을 판별하는 사람이 되는 것"**

README에 Emil이 직접 쓴 문장:

> *"All the skills here are a side-effect of domain-expertise. AI doesn't replace such expertise, it **amplifies** what you can get out of it and makes you way better relative to others."*
> (스킬은 전문성의 부산물이다. AI는 전문성을 대체하지 않고 **증폭**시키며, 상대적으로 훨씬 뛰어나게 만든다)

**스킬을 팔지 말고, 스킬을 쓸 수 있는 "전문성"을 팔아라.** 복제 불가능한 진짜 자산.

---

## 11. 한계와 주의사항

1. **마법이 아니다.** AI가 이 파일을 "읽을" 뿐. 안 읽으면 효과 0.
2. **웹 UI + 애니메이션에 90% 편중.** 백엔드·데이터·보안엔 도움 안 됨.
3. **한 사람의 취향이다.** 아주 좋은 취향이지만 절대 진리는 아님. 브랜드가 통통 튀는 걸 원하면 조정 필요.
4. **전부 영어.** (AI가 읽는 거라 기능엔 무관하지만, 사람이 학습하려면 번역 필요 → 수익화 모델 5)
5. **`.pl` 빈 파일**이 저장소에 있음. 정리해도 무방.
6. **포크 상태.** 업스트림 `emilkowalski/skills`가 업데이트되면 `git remote add upstream` 후 주기적 병합 권장.
7. **MIT 라이선스 준수.** 재배포·판매 시 `LICENSE` 원문과 저작권 고지 반드시 포함.

---

## 12. 참고 링크

### 저장소

- 내 포크: <https://github.com/bmshin94/emilkowalski-skills>
- 원본: <https://github.com/emilkowalski/skills>
- skills.sh 등록: <https://skills.sh/emilkowalski/skills>

### 원저작자

- 블로그: <https://emilkowal.ski>
- 7 Practical Animation Tips: <https://emilkowal.ski/ui/7-practical-animation-tips>
- Agents with Taste: <https://emilkowal.ski/ui/agents-with-taste>
- You Don't Need Animations: <https://emilkowal.ski/ui/you-dont-need-animations>
- 뉴스레터: <https://aiforui.dev/skills>

### 제작 라이브러리

- Sonner (토스트): <https://sonner.emilkowal.ski>
- Vaul (드로어): <https://vaul.emilkowal.ski>

### 이징 커브 도구

- <https://easing.dev/>
- <https://easings.co/>

### 설치

```bash
npx skills@latest add emilkowalski/skills
```

---

*이 문서는 2026-10-08 Claude Code 세션의 전수조사 대화를 정리한 것입니다.*
*원본 스킬의 저작권은 Emil Kowalski에게 있으며 MIT 라이선스를 따릅니다.*
