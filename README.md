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
<img src="https://img.shields.io/badge/AWS%20EC2%20·%20ECR%20·%20ECS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white"/>
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

- **결제 연동 (Bridge)** — 토스페이먼츠 결제 흐름 설계, 결제 상태 정합성 유지, 외부 API 장애 복구 구조
- **메시징** — 카카오 알림톡(Shoong) 연동, 발송 서버 분리·비동기 처리, 실패 재시도
- **어필리에이트** — 파트너별 트래킹·정산 구조 설계, 도메인 단위 기능 분리

---

## 💡 How I Work

- **왜 이 구조인가**를 먼저 고민하고 구현합니다
- 장애·로그·복구까지 고려한 **운영 관점**으로 개발합니다
- Swagger · Notion으로 **문서 기반 협업**을 합니다

🌱 **Currently Learning** — Java · Spring Boot · 대규모 트래픽 시스템 설계

---

<div align="center">

<a href="mailto:kimbona1148@gmail.com"><img src="https://img.shields.io/badge/Email-kimbona1148@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white"/></a>

</div>
