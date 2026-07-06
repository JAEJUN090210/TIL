# TIL - 07.06 / Web - Service Worker

## Summary

- **Service Worker는 브라우저 백그라운드에서 동작하며, 네트워크 요청을 제어하여 오프라인 지원, 캐싱, 푸시 알림 등의 기능을 제공하는 스크립트**

------

## Body

- **Service Worker**
  - 웹 페이지와 별도로 백그라운드에서 실행
  - 브라우저와 서버 사이의 프록시 역할 수행
  - 네트워크 요청을 가로채고(Cache, Fetch) 원하는 방식으로 응답 가능
- **주요 기능**
  - 정적 리소스 캐싱
  - 오프라인 지원
  - 네트워크 요청 제어
  - Push Notification
  - Background Sync
- **생명주기(Lifecycle)**
  1. **Register** : 브라우저에 Service Worker 등록
  2. **Install** : 필요한 리소스 캐싱
  3. **Activate** : 기존 캐시 정리 및 활성화
  4. **Fetch** : 네트워크 요청 처리
- **동작 특징**
  - DOM에 직접 접근할 수 없음
  - HTTPS 환경에서만 동작 (`localhost` 제외)
  - 브라우저가 별도의 스레드에서 실행
  - 페이지를 닫아도 일정 작업 수행 가능

------

## (+)

- 오프라인 환경에서도 서비스 제공 가능
- 캐싱을 통한 빠른 페이지 로딩
- 서버 요청 감소 및 성능 향상
- Push Notification 및 Background Sync 지원
- PWA 구현의 핵심 기술

------

## (-)

- 캐시 관리가 복잡할 수 있음
- 잘못된 캐싱 전략은 오래된 데이터를 제공할 수 있음
- 업데이트가 즉시 반영되지 않을 수 있음
- HTTPS 환경에서만 동작
- 