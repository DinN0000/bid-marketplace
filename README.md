# BidKit Marketplace

금융 IT 제안서 AI 에이전트 플러그인 마켓플레이스입니다.

## 설치 방법

Claude Code에서 아래 명령어를 실행하세요:

```
/plugin marketplace add https://github.com/DinN0000/bid-marketplace.git
/plugin install bid
```

## 설치 오류 시

`Permission denied (publickey)` 에러가 났다면, 터미널에서 아래 명령어로 실패한 캐시를 삭제한 뒤 다시 설치하세요:

```bash
rm -rf ~/.claude-256/plugins/marketplaces/DinN0000-bid-marketplace
```

그런 다음 Claude Code에서 위 설치 명령어를 다시 실행하면 됩니다.

## 포함된 플러그인

### bid (BidKit)

탑티어 수준의 기술 제안서를 전략 수립부터 최종 출력까지, 5개 전문 에이전트가 분업하여 작성하는 Claude Code 플러그인입니다.

**주요 기능:**
- RFP 분석 → 전략 수립 → 목차 생성
- 팀별 병렬 섹션 작성 (BA/DA/TA/SA)
- 교차 검증 (용어·수치·규정 일관성)
- 다중 포맷 출력 (MD/PDF/PPTX/HTML)

**명령어:**

| Command | Purpose |
|---------|---------|
| `/bid:design` | 전략 수립 + 목차 생성 |
| `/bid:write <section>` | 섹션 작성/수정 |
| `/bid:diagnose` | 전체 품질 진단 |
| `/bid:verify` | 교차 검증 |
| `/bid:status` | 진행 현황 |
| `/bid:setup` | 환경 점검 |

자연어도 됩니다: "RFP 받았는데 제안서 만들어야 해"

**소스:** [DinN0000/Harness](https://github.com/DinN0000/Harness)

## License

MIT
