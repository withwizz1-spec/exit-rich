# exit rich

퇴직금을 받은 MZ세대를 위한 투자 가이드 웹앱.
퇴직금 계산부터 비상금 분리, 투자 성향 진단, ETF 포트폴리오 추천, 자산 시뮬레이션까지 한 흐름으로 이어집니다.

## 주요 기능

| 단계 | 기능 |
|------|------|
| STEP 1 | 퇴직금 계산 (입사일·퇴직일·3개월 급여·연차수당 기반) |
| STEP 1.5 | ISA / 연금저축펀드 계좌 유무 확인 및 세액공제 시뮬레이션 |
| STEP 2 | 투자 성향 퀴즈 (보수형 / 안정형 / 성장형 / 공격형) |
| STEP 3 | 투자맵 — 성향·금액별 ETF 포트폴리오 추천 |
| STEP 4 | 미래 자산 시뮬레이션 (연 수익률·기간·일괄/분할 매수 설정) |
| STEP 5 | ETF 실시간 가격 트래킹 (Cloudflare Worker 프록시) |

- 비상금 계산기: 이직 상황별로 필요한 비상금을 먼저 제하고 투자 가능 금액 산출
- 퇴직금 산정 시 2월 포함 등 실제 달력 일수를 정확히 반영한 평균임금 계산
- 계좌별 비중 슬라이더로 연금저축펀드 / ISA / 일반 계좌 비율 직접 조정 가능
- 결과 화면에 confetti 애니메이션

## 기술 스택

- **React 19** + **Vite 8**
- **Recharts** — 포트폴리오 차트
- **Framer Motion** — 페이지 전환 애니메이션
- **canvas-confetti** — 퇴직금 계산 결과 confetti
- **Cloudflare Worker** — ETF 실시간 가격 프록시 (`exit-rich-price.withwizz1.workers.dev`)

## 로컬 실행

```bash
npm install
npm run dev
```

## 빌드

```bash
npm run build
npm run preview
```
