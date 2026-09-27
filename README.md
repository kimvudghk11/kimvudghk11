<div align="center">

# 안녕하세요, 백엔드 개발자 김평화입니다 👋

**비효율은 자동화로, 불확실성은 구조와 문서로 해결합니다.**

문제의 본질을 먼저 정의하고, 운영까지 버티는 구조로 해결하는 것을 좋아합니다.

<br/>

<img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white"/>
<img src="https://img.shields.io/badge/NestJS-E0234E?style=flat-square&logo=nestjs&logoColor=white"/>
<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white"/>
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white"/>
<img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/>
<img src="https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white"/>
<br/>
<img src="https://img.shields.io/badge/AWS%20EC2%20·%20ECS%20·%20ECR-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white"/>
<img src="https://img.shields.io/badge/CloudFront%20·%20ACM%20·%20Route%2053-8C4FFF?style=flat-square&logo=amazonwebservices&logoColor=white"/>
<img src="https://img.shields.io/badge/SQS-FF4F8B?style=flat-square&logo=amazonsqs&logoColor=white"/>
<img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/>
<br/>
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/>
<img src="https://img.shields.io/badge/Swagger-85EA2D?style=flat-square&logo=swagger&logoColor=black"/>
<img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white"/>
<img src="https://img.shields.io/badge/Notion-000000?style=flat-square&logo=notion&logoColor=white"/>

</div>

---

## 💳 Featured Project

### [payment-hub](https://github.com/kimvudghk11/payment-hub)
> 여러 서비스의 결제를 하나로 모으는 **결제 허브 서버** — NestJS · PostgreSQL · 토스페이먼츠

| 문제 | 해결 |
|---|---|
| PG 타임아웃으로 결제 결과를 모름 | 호출 **전** 선기록 → 결과 불명은 `UNKNOWN`으로 두고 대사 배치가 확정 |
| 동시 요청·재시도로 인한 이중 결제 | 주문 행 락 + 부분 유니크 인덱스 + 모든 쓰기에 멱등키 |
| 원장 금액 불일치·사후 조작 | 복식부기 원장, 차대 균형·append-only를 **DB 트리거**로 강제 |
| 결제 이벤트 유실·중복 전달 | Transactional Outbox + `SKIP LOCKED` 폴러 + HMAC 서명 웹훅 |

`API 43개` · `테이블 17개` · `테스트 약 530개 (실제 PostgreSQL 통합 274)`

---

## 🏢 Experience

### [Loword](https://github.com/kimvudghk11/LowordInc-Backend/blob/main/README.md) · Backend Developer
`2026.01.23 ~ 재직 중`

WordPress 호스팅 **브릿지**, 키워드 분석 SaaS **로워드**의 결제 · 정산 · 알림 · 서비스 간 동기화 담당

`레포 14개` · `커밋 1,271건` · `신규 서비스 1개 설계·구축`

#### ☁️ 인프라 · 배포
- **AWS 운영** — 사용자 EC2 인스턴스 **2,500대** 관리, CloudFront · ACM · Route 53을 서비스 단위로 운영
- **배포** — Docker 이미지 ECR 관리, ECS 기반 배포
- **호스팅 프로비저닝 개선** — WordPress 설치 구간 **4분 49초 → 54초** (스텝 계측으로 병목 확인 후 중복 작업 제거), EC2 **100대 동시 생성** 부하 테스트 도구 작성
- **과금 불일치 차단** — 원패스 상품에서 결제 확정 전 EC2가 생성되지 않도록 생성 게이트 설계, ACM 발급과 병렬화

#### 💳 결제
- **결제 원장 서비스(payment-ledger) 신규 설계·구축** — 주문 → 결제 → 취소 원장으로 결제 기록 통합
  - 호출 서비스가 발급한 멱등키로 중복 결제·취소 방어, 중복 요청은 `409`로 응답
  - 승인 후 적재 실패 시 망취소 + 주문 `FAILED` 전환으로 재시도가 영구 차단되던 문제 해결
- **결제 도메인 리팩터링** — 흩어진 금액 계산(할인·일할 환불)을 단일 서비스로 모으고 상품 ID 오사용 가드 추가
- 토스페이먼츠 정기결제·부분 환불·스케일 변경 결제, 환율 기반 USD 가격, 해외 카드 결제

#### 🤝 정산 · 동기화
- **파트너(어필리에이트) 정산** — 신청 → 심사 → 정산서 → 지급 흐름 구현, 정산 누락 버그 3건 원인 규명·수정
- **Transactional Outbox + SQS** — 레거시 Node.js 서비스의 결제·포인트 동기화를 트랜잭션 내 기록 + 순서 보장 발행으로 전환
- 동기화 워커의 벌크 upsert가 일부 컬럼을 NULL로 덮어쓰던 버그 수정

#### 📩 알림
- 카카오 알림톡 · 이메일 발송 배치, 실패 건 fallback queue 재처리, 5회 초과 시 `DEAD` 전환

---

## 💡 How I Work

- **측정 먼저, 최적화는 나중에** — 계측으로 병목을 확인한 뒤에 고칩니다
- **실패 경로의 끝 상태까지 정의합니다** — 재시도·재전달을 전제로 설계합니다
- **변경 이력은 원인 중심으로** — CHANGELOG에 원인 → 수정 → 검증을 남기고, 여러 레포에 걸친 변경은 배포 순서까지 적습니다
- **테스트하기 쉬운 구조로** — 복잡한 판정 로직은 순수 함수로 분리해 단위 테스트합니다

🌱 **Currently Learning** — Java · Spring Boot · 대규모 트래픽 시스템 설계

---

<div align="center">

<a href="mailto:kimbona1148@gmail.com"><img src="https://img.shields.io/badge/Email-kimbona1148@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white"/></a>

</div>
