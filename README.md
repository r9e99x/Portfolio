# 조준희 | iOS Developer Portfolio

> SwiftUI 기반 네이티브 iOS 앱을 직접 기획하고 구현하는 주니어 iOS 개발자, 조준희입니다.
> 두 개의 개인 프로젝트를 통해 Apple 플랫폼 기술 스택을 실전에 적용해왔으며,
> 궁극적으로는 일반 앱 개발을 넘어 **macOS/iOS 시스템·플랫폼·프레임워크 레벨 개발**을 목표로 하고 있습니다.

---

## 👋 About Me

- **학력**: 상지대학교 컴퓨터공학과 졸업
- **관심 분야**: SwiftUI / SwiftData / CoreML / SpriteKit 등 Apple 프레임워크, macOS·iOS 시스템 레벨 개발
- **GitHub**: [github.com/r9e99x](https://github.com/r9e99x)

---

## 📱 Projects

| | 🧩 Blocode | 💰 AI Money |
|---|---|---|
| 한 줄 소개 | 코드 블럭을 조립해 캐릭터를 목표 지점까지 이끄는 코딩 퍼즐 게임 | 직접 학습시킨 CoreML 모델 기반 AI 챗봇 스마트 가계부 |
| 플랫폼 | iOS / iPadOS / macOS | iOS |
| 핵심 기술 | SwiftUI, SpriteKit, MVVM, SwiftData | SwiftUI, SwiftData, CoreML·Create ML, Charts, MVVM |
| 개발 기간 | 진행 중 (App Store 출시 준비 단계) | 2025.03 ~ 2025.10 (7개월) |
| 저장소 | [github.com/r9e99x/Blocode](https://github.com/r9e99x/Blocode) | [github.com/r9e99x/AI-money](https://github.com/r9e99x/AI-money) |

---

## 🧩 Blocode

> 코드 블럭을 순서대로 조립해서 캐릭터를 목표 지점까지 이끄는 코딩 퍼즐 게임

코딩을 몰라도 즐길 수 있는 캐주얼 퍼즐이지만, 스테이지를 풀어가는 과정에서 순차 실행·반복문·조건문·함수 같은 프로그래밍 핵심 개념을 자연스럽게 체득하도록 설계했습니다. 블럭 하나하나가 실제 프로그래밍 문법과 1:1로 대응되어, 캐릭터의 움직임이 곧 "작성한 코드가 실행되는 모습"이 됩니다.

**핵심 컨셉**
- **블럭 = 코드**: 이동·회전 같은 기본 동작부터 `repeat`(반복), `if`(조건), `function`(함수) 같은 제어 구조까지 전부 드래그 앤 드롭으로 표현
- **별점 = 코드 품질**: 단순 클리어가 아니라 "더 적은 블럭으로 풀었는가"를 평가해, 반복문으로 압축할 줄 아는 사용자가 더 높은 점수를 받도록 설계
- **맵 = 실행 결과의 시각화**: 캐릭터 이동 경로가 곧 프로그램의 실행 트레이스이며, 실패 시 어느 블럭에서 막혔는지 하이라이트로 표시

**주요 기능**
- 9종 코드 블럭(이동/회전/반복/조건문/함수 + 보석·스위치 기믹), `repeat`↔`if` 최대 3단계 중첩 지원
- 10개 챕터·69개 스테이지 커리큘럼, 뒤로 갈수록 나선형 미로 등 알고리즘적 사고가 필요한 맵 등장
- 보석/스위치/포탈 기믹 시스템 — 정확한 위치에서 전용 블럭을 실행해야만 작동하는 "정밀한 프로그래밍" 요구
- 중첩 블럭 내부까지 추적하는 경로 기반 실행 하이라이트
- SwiftData 기반 진행도 저장, 챕터별 순차 해금
- 라이트/다크 모드, iPhone·iPad·Mac 화면 폭에 따른 반응형 레이아웃

**기술 스택 & 아키텍처**
- UI: SwiftUI (iOS/iPadOS/macOS 공용) · 맵/캐릭터 렌더링: SpriteKit
- 아키텍처: MVVM + Service 계층 + Scene 분리, `@MainActor` 격리
- 스테이지 데이터는 JSON으로 분리해 코드 수정 없이 콘텐츠 추가 가능
- Claude Code 기반 멀티 에이전트 워크플로우(XcodeBuildMCP, Xcode MCP, Context7)로 "동작 변경 없는 내부 구조 리팩터링" 진행

**개발 상태**: 챕터 1~10(69개 스테이지) 콘텐츠와 핵심 게임플레이 완성, App Store 심사 준비 중

👉 자세한 내용은 [Blocode 저장소](https://github.com/r9e99x/Blocode)에서 확인할 수 있습니다.

---

## 💰 AI Money — AI 기반 스마트 가계부

> 단순 지출 기록을 넘어, 직접 학습시킨 CoreML 텍스트 분류 모델과 컨텍스트 기반 대화형 챗봇을 결합한 스마트 가계부 앱

Create ML로 직접 학습시킨 텍스트 분류 모델(`ExpenseClassifier`)과 컨텍스트 기반 AI 챗봇을 결합해, 사용자의 지출 패턴을 자동으로 분석하고 자연어 대화로 재정 관리를 돕는 iOS 앱입니다.

**주요 기능**
- **지출 관리**: 캘린더 기반 지출 추가/조회, 다중 지출 일괄 입력, 카테고리별 분류(기본+커스텀), 한국 공휴일 자동 표시
- **AI 챗봇**: Create ML로 학습한 `ExpenseClassifier`가 질문 유형을 15가지로 분류, ML 분류와 정규식 기반 파싱을 결합한 하이브리드 처리, `ConversationContext`로 이전 대화의 기간·카테고리를 기억해 연속 질문 처리
- **데이터 시각화**: Charts 프레임워크 기반 카테고리별 차트, 월별/기간별 통계, 스프링 애니메이션이 적용된 상세 내역 뷰

**기술 스택 & 설계**
- Swift(SwiftUI) 기반 네이티브 개발, SwiftData(`@Model`, `FetchDescriptor`, `@ModelActor`)로 로컬 데이터 관리
- CoreML/Create ML — 지출 질문 분류 모델 직접 학습 및 통합
- MVVM + Protocol-Oriented Programming(`ExpenseServiceProtocol` 등으로 인터페이스 추상화)
- `@MainActor`로 UI 스레드 안전성, `@ModelActor` 기반 `DataActor`로 SwiftData 비동기 접근 안전성 확보
- `CalendarState` enum, `DailyExpenseSummary`, 공통 `FormatHelper` 등 데이터/포맷 로직 구조화

**개발 정보**: 2025.03 ~ 2025.10 (7개월), 버전 1.0 beta

👉 자세한 내용은 [AI Money 저장소](https://github.com/r9e99x/AI-money)에서 확인할 수 있습니다.

---

## 🛠 종합 기술 스택

| 구분 | 사용 기술 |
|---|---|
| 언어 | Swift |
| UI 프레임워크 | SwiftUI |
| 게임/렌더링 | SpriteKit |
| 데이터 | SwiftData |
| 머신러닝 | CoreML, Create ML |
| 시각화 | Charts |
| 아키텍처 | MVVM, Protocol-Oriented Programming |
| 동시성 | `@MainActor`, `@ModelActor` |
| 개발 도구 | Xcode, Claude Code(멀티 에이전트 리팩터링 워크플로우) |

---

## 📫 Contact

- **GitHub**: [github.com/r9e99x](https://github.com/r9e99x)
- **EMail**: r94509@gmail.com

---

<div align="center">

이 저장소는 조준희의 iOS 개발 포트폴리오 인덱스입니다.<br>
각 프로젝트의 전체 코드와 문서는 위 링크의 개별 저장소에서 확인하실 수 있습니다.

</div>
