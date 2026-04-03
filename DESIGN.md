# Design System — 리뷰천사

## Product Context
- **What this is:** 소상공인 이커머스 셀러 대상 AI 리뷰 답변 + 전화 CS 대행 서비스
- **Who it's for:** 혼자 다 하는 쿠팡/네이버 셀러. CS 직원 채용이 부담되는 소상공인
- **Space/industry:** 이커머스 CS 대행, 리뷰 관리
- **Project type:** Marketing site + Web app (SaaS)

## Aesthetic Direction
- **Direction:** Organic/Warm
- **Decoration level:** Intentional
- **Mood:** 따뜻하고 인간적. "내 편이 되어주는 서비스" 느낌. 경쟁사(챗봇나우, 바리뷰)가 전부 테크 블루이므로, 의도적으로 따뜻한 톤으로 차별화.
- **Anti-patterns:** 퍼플/인디고 그라데이션, 둥근 카드 그리드, 체크리스트 나열, AI 슬롭 패턴 금지

## Typography
- **Display/Hero:** Noto Sans KR (800) — 한국 소상공인에게 가장 익숙한 서체
- **Body:** Pretendard — 토스/카카오/네이버 등 한국 서비스 표준
- **UI/Labels:** Pretendard
- **Data/Tables:** Pretendard (tabular-nums)
- **Loading:** CDN (jsdelivr + Google Fonts)
- **Scale:** Hero 4rem, H2 2.4rem, Body 1.6rem, Small 1.3rem, Caption 1.1rem

## Color
- **Approach:** Restrained (1 accent + warm neutrals)
- **Primary:** #E8631A — 따뜻한 오렌지. 에너지 + 친근함. 배민 느낌.
- **Primary hover:** #D4570F
- **Primary bg:** #FFF4ED
- **Neutrals:** Warm gray 계열
  - Background: #FAFAF8
  - Surface: #F5F3EF
  - Border: #E8E4DE
  - Heading: #1A1A1A
  - Body: #4A4A4A
  - Muted: #8A8A8A
- **Semantic:** success #2D8F4E, warning #E8A817, error #D94040

## Spacing
- **Base unit:** 8px
- **Density:** Comfortable
- **Scale:** 2xs(2) xs(4) sm(8) md(16) lg(24) xl(32) 2xl(48) 3xl(64)

## Layout
- **Approach:** Grid-disciplined
- **Max content width:** 1080px (요금제 섹션은 1120px)
- **Border radius:** sm:6px, md:8px, lg:12px, xl:16px (둥글지만 과하지 않게)

## Motion
- **Approach:** Minimal-functional
- **Easing:** ease-out (enter), ease-in (exit)
- **Duration:** micro 100ms, short 200ms

## Voice & Language
- "사장님" 호칭 적극 사용
- 테크 용어 최소화 (에이전트, RAG, 에스컬레이션 → 전문 상담사, AI 답변, 알림)
- 공감형 톤 ("혼자 다 하시죠?", "사장님은 상품에만 집중하세요")
- 비용 비교는 구체적 항목 나열 (급여 215만원 + 4대보험 + 퇴직금 + 식대 + 연차수당)

## Pricing (2026-04-03)
| 티어 | 가격 | 핵심 |
|------|------|------|
| 스타터 | 9,900원/월 | AI 답변 맛보기 |
| 베이직 | 59,000원/월 | AI 완전 자동 |
| 스탠다드 | 250,000원/월 | AI + 전화 CS 시작 |
| 프로 | 390,000원/월 | CS 걱정 끝 |
| 엔터프라이즈 | 별도 협의 | 전담팀 운영 |

## Decisions Log
| Date | Decision | Rationale |
|------|----------|-----------|
| 2026-04-03 | 인디고 → 오렌지 컬러 전환 | 경쟁사 전부 블루/인디고. 소상공인 친화 따뜻한 톤으로 차별화 |
| 2026-04-03 | 카드리스 디자인 | AI 슬롭(둥근 카드 그리드) 탈출 |
| 2026-04-03 | "사장님" 언어 채택 | 타겟이 소상공인. 테크 용어 대신 일상 언어 |
| 2026-04-03 | 요금제 5개 한번에 표시 | 숨김 없이 투명하게. 셀러가 바로 비교 가능 |
| 2026-04-03 | 스탠다드 25만/프로 39만 | 직원 300만원 대비 1/12. CS 외주 대비도 합리적 가격 |
