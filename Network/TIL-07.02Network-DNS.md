# TIL - 07.02 / Network - DNS

## Summary

- **DNS(Domain Name System)는 사람이 사용하는 도메인 이름을 컴퓨터가 사용하는 IP 주소로 변환하는 시스템**

------

## Body

- **DNS**
  - 도메인 이름을 IP 주소로 변환(Name Resolution)
  - 계층 구조로 관리되어 빠르고 효율적인 조회 가능
- **도메인 구조**
  - Root (`.`)
  - TLD (Top-Level Domain): `.com`, `.kr`
  - 등록 도메인: `example.com`, `example.co.kr`
  - 서브도메인: `www`, `api`, `blog`
- **DNS 구성 요소**
  - **DNS Resolver** : DNS 조회 및 캐싱 수행
  - **Root Name Server** : TLD 서버 위치 안내
  - **TLD Name Server** : 권한 DNS 위치 안내
  - **Authoritative Name Server** : 실제 DNS 레코드 반환
- **주요 DNS 레코드**
  - **A** : 도메인 → IPv4
  - **AAAA** : 도메인 → IPv6
  - **CNAME** : 도메인 별칭
  - **MX** : 메일 서버
  - **NS** : 권한 네임서버
  - **TXT** : 인증 및 검증 정보
  - **PTR** : IP → 도메인(역방향 조회)
- **DNS 캐싱과 TTL**
  - 조회 결과를 일정 시간 캐싱하여 속도 향상
  - **TTL(Time To Live)** 이 길수록 조회는 빠르지만 변경 사항 반영이 늦음
- **동작 과정**
  1. 브라우저/OS 캐시 확인
  2. DNS Resolver 질의
  3. Root Server 조회
  4. TLD Server 조회
  5. Authoritative Server에서 IP 반환
  6. 캐싱 후 IP로 서버 접속

------

## (+)

- 사람이 기억하기 쉬운 도메인 사용 가능
- DNS 캐싱으로 조회 속도 향상
- 계층 구조로 확장성과 관리 효율성이 높음
- 도메인과 서버(IP)를 분리하여 운영 가능

------

## (-)

- DNS 서버 장애 시 이름 해석 불가
- TTL이 길면 변경 사항 반영이 늦음
- 잘못된 DNS 설정은 서비스 장애를 유발할 수 있음
- DNS 스푸핑, 캐시 포이즈닝 등의 보안 공격 대상이 될 수 있음