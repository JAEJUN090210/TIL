# TIL - 07.03 / DevOps - Argo CD

## Summary

- **Kubernetes 환경에서 Git 저장소를 기준(Source of Truth)으로 애플리케이션을 자동 배포하고 동기화하는 GitOps 기반의 CD(Continuous Delivery) 도구**

------

## Body

- **Argo CD**
  - Kubernetes 전용 GitOps 배포 도구
  - Git에 저장된 매니페스트(YAML, Helm, Kustomize 등)를 클러스터와 자동 동기화
  - 선언형(Declarative) 방식으로 애플리케이션 관리
- **GitOps**
  - Git을 시스템의 단일 진실 공급원(Source of Truth)으로 사용
  - Git 변경 사항을 기준으로 배포 및 롤백 수행
  - 운영 환경과 Git 상태를 항상 일치하도록 유지
- **주요 기능**
  - 자동 배포(Auto Sync)
  - Drift Detection(설정 변경 감지)
  - Self Heal(클러스터 변경 사항 자동 복구)
  - Rollback(이전 버전 복원)
  - 배포 이력 및 상태 시각화
- **배포 흐름**
  1. 개발자가 Git에 코드 또는 매니페스트 Push
  2. CI에서 Docker 이미지 빌드 및 Registry 업로드
  3. Git의 이미지 태그 또는 매니페스트 업데이트
  4. Argo CD가 변경 사항 감지
  5. Kubernetes 클러스터에 자동 동기화 및 배포

------

## (+)

- Git만으로 배포 상태 관리 가능
- 자동 배포 및 자동 복구 지원
- Git과 클러스터 상태를 항상 일치시킴
- 롤백과 변경 이력 관리가 쉬움
- Web UI를 통한 배포 상태 확인 가능

------

## (-)

- Kubernetes 환경에서만 사용 가능
- GitOps 개념에 대한 이해가 필요
- 잘못된 Git 변경 사항도 자동 배포될 수 있음
- 초기 구축 및 권한 관리가 다소 복잡함