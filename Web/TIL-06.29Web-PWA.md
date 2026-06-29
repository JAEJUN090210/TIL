# TIL - 06.29 / Web - PWA

## Summary

- **PWA(Progressive Web App)는 웹 애플리케이션을 네이티브 앱처럼 사용할 수 있도록 만드는 웹 기술**

------

## Body

- **PWA**
  - 웹 앱을 설치 가능한 앱처럼 제공
  - 오프라인 사용 및 백그라운드 기능 지원
  - 웹 기술(HTML, CSS, JavaScript) 기반
- **Manifest**
  - 앱의 이름, 아이콘, 시작 페이지 등 메타데이터 정의
  - 브라우저가 앱으로 인식하는 기준
  - 설치 기능을 위해 필수
- **Service Worker**
  - 브라우저 백그라운드에서 실행되는 스크립트
  - 네트워크 요청 가로채기
  - 캐싱 및 오프라인 지원
  - Push Notification 처리
  - HTTPS 환경에서만 동작
- **Cache Storage**
  - Service Worker가 사용하는 저장소
  - 정적 파일 및 API 응답 캐싱 가능
- **주요 캐싱 전략**
  - **Cache First** : 캐시 우선 (정적 리소스)
  - **Network First** : 네트워크 우선 (API)
  - **Stale While Revalidate** : 캐시 즉시 제공 후 백그라운드 업데이트
- **React + Vite 구성**
  - `vite-plugin-pwa` 사용
  - Manifest 및 Service Worker 자동 생성
  - Workbox를 통한 캐싱 전략 설정 가능

------

## (+)

- 앱 설치 가능
- 오프라인 사용 가능
- 빠른 로딩 속도
- 푸시 알림 지원
- 하나의 코드베이스로 웹과 앱 경험 제공

------

## (-)

- HTTPS 환경이 필수
- 브라우저별 지원 기능 차이 존재
- Service Worker 캐시로 인해 업데이트가 즉시 반영되지 않을 수 있음
- 캐싱 전략을 잘못 설정하면 오래된 데이터를 제공할 수 있음