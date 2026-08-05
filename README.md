# 개발자 작업실 꾸미기 — Codyssey AI 올인원 2기 1주차

## 1. 프로젝트 개요
터미널, Docker(OrbStack), Git/GitHub을 활용해 재현 가능한 개발 워크스테이션을 구축한다.

## 2. 실행 환경
- OS: macOS
- Shell: zsh
- Docker: 28.5.2 (OrbStack 기반)
- Git: 2.53.0

## 3. 수행 체크리스트
- [x] 터미널 기본 조작 및 폴더 구성
- [ ] 파일/디렉토리 권한 변경 실습
- [x] Docker 설치 및 점검 (`docker --version`, `docker info`)
- [ ] Docker 기본 운영 명령 (images/ps/logs/stats)
- [ ] hello-world / ubuntu 컨테이너 실행
- [ ] Dockerfile 기반 커스텀 이미지 빌드
- [ ] 포트 매핑 접속 확인 (2회)
- [ ] 바인드 마운트 반영 확인
- [ ] 볼륨 영속성 검증
- [x] Git 설정 및 GitHub 연동

## 4. 검증 방법
(각 항목 진행하면서 채워나갈 예정)

## 5. 트러블슈팅

### 1) `docker info` 명령어 오타
- 문제: `docker info` 대신 `doker info`를 입력해 `command not found` 에러 발생
- 원인 가설: 명령어 철자 오타
- 확인: 입력 내용 재확인 → `docker`에서 `c` 누락 확인
- 해결: 정확한 철자로 재입력 → 정상 작동

### 2) `mkdir` 이후 `quote>` 프롬프트에서 멈춤
- 문제: 폴더 생성 명령 뒤 터미널이 `quote>` 상태로 멈춰 이후 명령이 실행되지 않음
- 원인 가설: 명령어 끝에 의도치 않은 작은따옴표(`'`)가 추가되어 따옴표 짝이 맞지 않음
- 확인: 입력 내용 재확인 → 여분의 `'` 발견
- 해결: `Ctrl+C`로 입력 취소 후 따옴표 없이 재입력

### 3) `.gitignore` 저장 후에도 내용이 비어있음
- 문제: `cat .gitignore` 결과가 빈 값으로 나옴
- 원인 가설: VSCode 편집창에서 `Cmd+S` 저장이 정상적으로 반영되지 않음
- 확인: VSCode 탭에 저장 안 됨을 나타내는 점(●) 표시 확인
- 해결: 편집창 클릭 후 재입력 및 재저장 → 정상 반영