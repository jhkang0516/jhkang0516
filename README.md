### 운영 중인 서비스의 성능·동시성·배포 문제를 해결하는 Java·Spring 백엔드 개발자

맛집 지도 앱 **[핀디쉬](https://apps.apple.com/kr/app/id6811157600)** 의 백엔드와 인프라를 혼자 설계해 App Store에 출시하고 운영합니다.

문제는 실행 계획·부하 테스트·동시성 테스트로 재현하고, 고친 결과도 같은 방법으로 확인합니다.

[![App Store](https://img.shields.io/badge/App_Store-핀디쉬-0D96F6?style=flat&logo=appstore&logoColor=white)](https://apps.apple.com/kr/app/id6811157600)
[![Velog](https://img.shields.io/badge/Velog-기술_블로그-20C997?style=flat&logo=velog&logoColor=white)](https://velog.io/@jhkang0516)

---

#### 백엔드에서 풀어낸 문제

- **검색 성능** — 53만 행 가게 테이블에서 두 글자 검색 0.9초 → 0.1초. bigram GIN 인덱스와 검색어 길이별 SQL 분기 · [PinDish](https://github.com/jhkang0516/pindish)
- **동시성** — Hibernate 비관 잠금이 `FOR NO KEY UPDATE`로 실행돼 자식 INSERT를 막지 못하는 문제를 찾아 네이티브 `FOR UPDATE`로 수정 · [PinDish](https://github.com/jhkang0516/pindish)
- **배포 안정성** — 단일 EC2 블루·그린 배포, 위험한 DDL은 CI에서 차단하고 스키마 변경은 이전 코드와 호환되게 나눠 배포 · [PinDish](https://github.com/jhkang0516/pindish)
- **JVM 메모리** — 동시 업로드 부하 테스트로 힙 밖 direct buffer OOM의 원인을 찾아 해소, 프로세스 최고 메모리 26% 감소 · [PinDish](https://github.com/jhkang0516/pindish)
- **읽기·쓰기 분리** — `readOnly` 트랜잭션을 Replica로 라우팅, 커버링 인덱스·DTO 프로젝션까지 더해 k6 평균 응답 605 → 360ms · [foodcom](https://github.com/jhkang0516/foodcom)

#### 경력 · 수상

- 💼 **래브라도랩스** 인턴 (재직 중)
- 🏆 아주대학교 **캡스톤디자인 우수상 (2위)** — [ostone](https://github.com/ajou-2026-1-capstone-5/ostone)
- 🏆 아주대학교 **하계 모각소 장려상**

#### 프로젝트

| 프로젝트 | 백엔드 담당 |
|---|---|
| [**PinDish**](https://github.com/jhkang0516/pindish) · App Store 운영 중 | 1인 개발. Spring Boot·PostGIS API, 공공데이터 53만 건 적재 배치, AWS 운영 |
| [**foodcom**](https://github.com/jhkang0516/foodcom) · F-Lab | 1인 백엔드. Cloud Run, Cloud SQL 읽기·쓰기 분리, Redis 토큰 저장, k6 부하 테스트 |
| [**ostone**](https://github.com/ajou-2026-1-capstone-5/ostone) · 캡스톤 우수상 | AI 상담 시스템의 도메인팩 API, LLM 상담 도구, 메시지 순서 경합 수정 |

#### Stack

- **Backend** Java 21 · Spring Boot · JPA / Hibernate · PostgreSQL / PostGIS · Flyway · Redis
- **Infra** AWS (EC2 · RDS · CloudFront) · GCP (Cloud Run · Cloud SQL) · Docker · nginx
- **CI/CD** GitHub Actions · Jenkins
- **Test·Ops** PostGIS 컨테이너 통합 테스트 · k6 · Sentry
