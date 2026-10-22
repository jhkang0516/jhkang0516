## 강준현

**백엔드를 중심으로 앱·인프라·AI까지, 아이디어를 출시된 서비스로 만드는 개발자입니다.**

맛집 지도 앱 [핀디쉬](https://apps.apple.com/kr/app/id6811157600)를 혼자 설계·개발해 App Store에 출시하고 운영하고 있습니다.

문제는 실행 계획·부하 테스트·실측으로 재현하고, 고친 결과도 같은 방법으로 확인합니다.

[![App Store](https://img.shields.io/badge/App_Store-핀디쉬-0D96F6?style=flat-square&logo=appstore&logoColor=white)](https://apps.apple.com/kr/app/id6811157600)
[![Velog](https://img.shields.io/badge/Velog-기술_블로그-20C997?style=flat-square&logo=velog&logoColor=white)](https://velog.io/@jhkang0516)

- 💼 **래브라도랩스** 인턴 · 재직 중
- 🏆 아주대학교 **캡스톤디자인 우수상 (2위)** · [ostone](https://github.com/ajou-2026-1-capstone-5/ostone)
- 🏆 아주대학교 **하계 모각소 장려상**

---

### What I do

- **Backend** — Spring Boot · JPA / Hibernate · PostgreSQL / PostGIS
  - 53만 행 가게 테이블의 두 글자 검색 0.9초 → 0.1초: bigram 표현식 GIN 인덱스, 검색어 길이별 SQL 분기로 범용 실행 계획 회피
  - Hibernate `PESSIMISTIC_WRITE`가 `FOR NO KEY UPDATE`로 실행돼 외래 키 검사와 충돌하지 않는 문제를 찾아 네이티브 `FOR UPDATE`로 수정
  - 요청마다 후보 전체를 정렬하던 추천 피드를 구간별 제한 조회 + 부분 인덱스로 교체
  - `RoutingDataSource` + `LazyConnectionDataSourceProxy`로 `readOnly` 트랜잭션을 Replica로 라우팅 (foodcom)
- **Infra** — AWS (EC2 · RDS · CloudFront) · GCP Cloud Run · Docker · nginx
  - 단일 EC2 nginx 블루·그린 배포: 새 컨테이너 헬스 체크 후 업스트림 전환, 실패하면 기존 컨테이너 유지
  - 이전 버전 코드와 호환되는 마이그레이션 규칙과 위험 DDL CI 검사, `CREATE INDEX CONCURRENTLY`와 Flyway 잠금의 교착 해결
  - 2GB 인스턴스 JVM 튜닝: direct buffer 캐시 제한·glibc arena 축소로 업로드 OOM 해소, 최고 메모리 26% 감소, G1GC 명시
- **App** — Expo·React Native iOS 앱 개발·출시. 릴스·네이버 지도 공유로 가게 저장, 지도 화면
- **AI·Data** — 주소 + LLM 장소 매칭(매칭률 62% → 77%), 릴스 캡션 요약, 임베딩·HDBSCAN 상담 의도 분석

### Projects

| 프로젝트 | 설명 | 역할 |
|---|---|---|
| **[PinDish](https://github.com/jhkang0516/pindish)** | 목적별 맛집 지도 앱 · App Store 운영 중 | 1인 개발 (백엔드·앱·인프라) |
| **[foodcom](https://github.com/jhkang0516/foodcom)** | 음식 커뮤니티 · GCP Cloud Run, 읽기·쓰기 DB 분리·쿼리 튜닝, k6 평균 응답 605 → 360ms | 백엔드 |
| **[ostone](https://github.com/ajou-2026-1-capstone-5/ostone)** | 상담 로그로 AI 상담 워크플로우를 만드는 시스템 · 캡스톤 우수상 | 백엔드·LLM 파이프라인 |
| **[dialect_classification](https://github.com/jhkang0516/dialect_classification)** | 6개 지역 방언 음성 분류 (MFCC · ResNeXt50) | ML |

### Stack

- **Backend** Java · Spring Boot · JPA / Hibernate · PostgreSQL / PostGIS · Redis
- **App** React Native · Expo · TypeScript · TanStack Query
- **Infra** AWS (EC2 · RDS · CloudFront) · GCP (Cloud Run · Cloud SQL) · Docker · nginx · GitHub Actions · Jenkins
- **AI·Data** Python · OpenAI API · 임베딩 · HDBSCAN · PyTorch
