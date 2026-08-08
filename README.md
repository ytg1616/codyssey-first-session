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
- [x] 파일/디렉토리 권한 변경 실습
- [x] Docker 설치 및 점검 (`docker --version`, `docker info`)
- [x] Docker 기본 운영 명령 (images/ps/logs/stats)
- [x] hello-world / ubuntu 컨테이너 실행
- [x] Dockerfile 기반 커스텀 이미지 빌드
- [x] 포트 매핑 접속 확인 (2회)
- [x] 바인드 마운트(외부 저장) 반영 확인
- [x] 볼륨 영속성 검증
- [x] Git 설정 및 GitHub 연동

## 4. 검증 방법
- Git 설정: `git config --list` 실행 결과

\`\`\`
user.name= ytg1616
user.email= ytg1616@gmail.com
init.defaultbranch=main
...
\`\`\`

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

## 6. 증거 자료
스크린샷 모음(구글드라이브): (https://docs.google.com/document/d/17iRntgpWm7rpi_XvH7fv2XckVY34P0wPGTAen4aknfo/edit?tab=t.0)

## 7. 학습 노트 (핵심 개념 정리)

- **GUI vs CLI**: GUI는 마우스로 클릭, CLI(Command Line Interface)는 명령어로 지시.
  반복 작업(예: 폴더 100개 생성)은 CLI가 압도적으로 빠르고, 서버처럼 GUI가 아예 없는 환경도 많음.
- **Shell**: 터미널에 입력한 명령어를 운영체제가 이해할 수 있게 번역해주는 프로그램. 이번 과제에서 쓰는 shell은 zsh.
- **명령어 흐름**: 쉘 명령어 → OS에 직접 지시. 반면 코딩 언어는 프로그램/앱을 만들 때 사용 — 즉 "터미널 위에서 프로그래밍 언어가 돌아가는" 구조.
- **명령어 어원**
  - `cd` = Change Directory (디렉토리=폴더)
  - `ls` = list
  - `-` (플래그/옵션) = 명령어의 세부 동작 지정. 예: `ls -l` = list + long(자세히)
  - `>` = 터미널 출력 대신 다른 곳으로 보내기 (redirection)
