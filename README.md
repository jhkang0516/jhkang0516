### Java·Spring 백엔드 개발자 — 앱을 혼자 만들어 출시하고 운영합니다

맛집 지도 앱 **[핀디쉬](https://apps.apple.com/kr/app/id6811157600)** 를 기획부터 백엔드·앱·AWS 인프라까지 혼자 개발해 App Store에 출시했습니다.

검색 성능, 데이터 정합성, 배포 안정성처럼 실제 운영에서 생기는 문제를 끝까지 파고듭니다.

[![App Store](https://img.shields.io/badge/App_Store-핀디쉬-0D96F6?style=flat&logo=appstore&logoColor=white)](https://apps.apple.com/kr/app/id6811157600)
[![Velog](https://img.shields.io/badge/Velog-기술_블로그-20C997?style=flat&logo=velog&logoColor=white)](https://velog.io/@jhkang0516)

---

#### 📍 [PinDish](https://github.com/jhkang0516/pindish) — 1인 개발 · App Store 운영 중

개발 3개월 동안 PR 129개를 머지하며 출시와 업데이트를 이어 가고 있습니다.

- **검색** 한국어 두 글자 검색 쿼리 0.9초 → 0.1초 (bigram 인덱스, 실행 계획 분리)
- **데이터** 공공데이터 가게 53만 건 적재, 공유된 장소 목록 매칭률 62% → 77% (주소로 좁힌 뒤 LLM 판정, 확인된 오매칭 0건)
- **배포** 단일 EC2 블루·그린 무중단 배포, 비호환 스키마 변경은 CI에서 차단
- **자동화** 머지하면 TestFlight, 버전을 올리면 App Store 심사까지 자동 제출

Claude Code·Codex를 워크트리별로 병렬 운용하고, CI와 자동 코드리뷰를 통과해야 머지합니다. 에이전트가 만든 변경은 실행 계획과 동시성 테스트로 직접 검증합니다.

#### 그 밖의 프로젝트

| 프로젝트 | 담당 · 성과 |
|---|---|
| [**foodcom**](https://github.com/jhkang0516/foodcom) · F-Lab | 1인 백엔드. GCP 읽기·쓰기 DB 분리, k6 부하 테스트로 평균 응답 **605 → 360ms**, 에러율 **14% → 0%** |
| [**ostone**](https://github.com/ajou-2026-1-capstone-5/ostone) · 아주대 캡스톤 | 상담 로그에서 의도·정책을 뽑아내는 AI 상담 시스템. 의도 발견 파이프라인과 LLM 상담 도구 담당 |
| [**dialect_classification**](https://github.com/jhkang0516/dialect_classification) | 방언 음성 6만 건, MFCC + ResNeXt50으로 6개 지역 분류 테스트 정확도 **90%** |

#### Stack

- **Backend** Java · Spring Boot · JPA · PostgreSQL / PostGIS
- **App** React Native · Expo · TypeScript
- **Infra** AWS · Docker · nginx · GitHub Actions
- **ML** Python · LLM 파이프라인 · 임베딩·클러스터링
