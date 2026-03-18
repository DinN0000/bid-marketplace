# BidKit Marketplace

> **금융 IT 제안서를 AI 에이전트 팀이 분업하여 작성하는 Claude Code 플러그인**

RFP(제안요청서)를 받으면 전략 수립부터 목차 설계, 섹션별 병렬 작성, 교차 검증, 최종 포맷 출력까지 — 5개 전문 에이전트가 협업하여 탑티어 수준의 기술 제안서를 만들어 줍니다.

---

## 주요 기능

| 기능 | 설명 |
|------|------|
| **RFP 분석** | 제안요청서를 파싱하여 핵심 요구사항·평가 기준·제약 조건 추출 |
| **전략 수립 + 목차 생성** | 분석 결과 기반으로 제안 전략과 목차를 자동 설계 |
| **팀별 병렬 작성** | BA(비즈니스) · DA(데이터) · TA(기술) · SA(솔루션) 에이전트가 섹션 분담 |
| **교차 검증** | 용어·수치·규정 일관성을 자동 진단 |
| **다중 포맷 출력** | Markdown · PDF · PPTX · HTML 변환 지원 |

---

## 사전 요구사항

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI가 설치되어 있어야 합니다
- Claude Code **플러그인 기능** 활성화 필요 (Claude Code 최신 버전 권장)

---

## 설치 방법

Claude Code 터미널에서 아래 두 명령어를 순서대로 실행하세요:

```
/plugin marketplace add https://github.com/hwaa-lee/bid-marketplace.git
/plugin install bid
```

설치가 완료되면 `/bid:setup`으로 환경이 제대로 구성되었는지 확인할 수 있습니다.

### 설치 오류 해결

`Permission denied (publickey)` 에러가 발생하면, 캐시된 실패 데이터를 삭제 후 재설치하세요:

```bash
# 캐시 삭제
rm -rf ~/.claude-256/plugins/marketplaces/hwaa-lee-bid-marketplace

# Claude Code에서 다시 설치
/plugin marketplace add https://github.com/hwaa-lee/bid-marketplace.git
/plugin install bid
```

---

## 사용법

### 슬래시 명령어

| 명령어 | 설명 |
|--------|------|
| `/bid:setup` | 환경 점검 — 필요한 도구가 모두 설치되었는지 확인 |
| `/bid:design` | 전략 수립 + 목차 생성 — RFP를 분석하고 제안 구조를 설계 |
| `/bid:write <section>` | 섹션 작성/수정 — 특정 섹션을 작성하거나 수정 |
| `/bid:diagnose` | 품질 진단 — 교차 검증으로 일관성 체크 |
| `/bid:status` | 진행 현황 — 전체 제안서 작성 상태 확인 |

### 자연어로도 사용 가능

명령어를 외울 필요 없이 자연어로 말해도 됩니다:

```
"RFP 받았는데 제안서 만들어야 해"
"기술 아키텍처 섹션 다시 써줘"
"지금까지 진행 상황 보여줘"
"전체 품질 검증해줘"
```

### 일반적인 워크플로

```
1. RFP 문서를 프로젝트 폴더에 넣기 (PDF/DOCX/MD)
2. /bid:design          ← RFP 분석 → 전략 수립 → 목차 생성
3. /bid:write 개요       ← 섹션별 작성 (반복)
4. /bid:write 기술제안
5. /bid:write 사업관리
6. /bid:diagnose         ← 교차 검증
7. /bid:status           ← 최종 확인
```

---

## 플러그인 삭제

```
/plugin uninstall bid
```

마켓플레이스 자체를 제거하려면:

```
/plugin marketplace remove bid-marketplace
```

---

## 프로젝트 구조

```
bid-marketplace/
├── .claude-plugin/
│   └── marketplace.json    ← 마켓플레이스 메타데이터 및 플러그인 목록
└── README.md
```

실제 BidKit 플러그인 소스 코드는 설치 시 [bidkit 리포지토리](https://github.com/DinN0000/bidkit)에서 자동으로 다운로드됩니다.

---

## 라이선스

MIT
