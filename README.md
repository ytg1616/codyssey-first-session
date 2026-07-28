# codyssey-first-session

PS C:\Users\n> # 1. "나 지금 어디 있어?" (현재 위치 확인 - 절대 경로)
>> pwd
>> 

Path      
----      
C:\Users\n
n@PC-191222 MINGW64 ~
$ # 2. "여기 무슨 파일들이 있어? 숨김 파일까지 다 보여줘" (목록 확인)
ls -al
total 204262
drwxr-xr-x 1 n 197121         0 Jul 28 17:31  ./
drwxr-xr-x 1 n 197121         0 Dec 14  2020  ../
drwxr-xr-x 1 n 197121         0 Apr  4  2021  .android/
drwxr-xr-x 1 n 197121         0 May 29 19:10  .claude/
-rw-r--r-- 1 n 197121     22237 May 29 19:10  .claude.json
drwxr-xr-x 1 n 197121         0 Jul 28 17:35  .copilot/
drwxr-xr-x 1 n 197121         0 Jul 25 12:02  .cua-driver/
drwxr-xr-x 1 n 197121         0 Jul 26 12:35  .cua-driver-rs/
-rw-r--r-- 1 n 197121       113 Jul 28 17:31  .gitconfig
drwxr-xr-x 1 n 197121         0 Jul 25 01:19  .local/
drwxr-xr-x 1 n 197121         0 Mar 17  2020  .Origin/
(생략)

n@PC-191222 MINGW64 ~
$ # 3. "test_folder 라는 이름의 새 상자(폴더)를 만들어줘" (생성)
mkdir test_folder

n@PC-191222 MINGW64 ~
$ # 4. "test_folder 안으로 들어갈래" (이동 - 상대 경로)
cd test_folder

n@PC-191222 MINGW64 ~/test_folder
$ # 5. "hello.txt 라는 빈 종이(파일)를 만들어줘" (빈 파일 생성)
touch hello.txt

n@PC-191222 MINGW64 ~/test_folder
$ # 6. "hello.txt 복사해서 copy.txt 하나 더 만들어줘" (복사)
cp hello.txt copy.txt

n@PC-191222 MINGW64 ~/test_folder
$ # 7. "copy.txt 이름을 rename.txt 로 바꿔줘" (이름 변경/이동)
mv copy.txt rename.txt

n@PC-191222 MINGW64 ~/test_folder
$ 1s -al
bash: 1s: command not found

n@PC-191222 MINGW64 ~/test_folder
$ ls -al
total 24
drwxr-xr-x 1 n 197121 0 Jul 28 17:44 ./
drwxr-xr-x 1 n 197121 0 Jul 28 17:43 ../
-rw-r--r-- 1 n 197121 0 Jul 28 17:43 hello.txt
-rw-r--r-- 1 n 197121 0 Jul 28 17:44 rename.txt

n@PC-191222 MINGW64 ~/test_folder
$ rm rename.txt


### 🚨 트러블슈팅 1: 터미널 명령어 `ls -al` 인식 불가 오류

* **문제 상황:** VS Code 터미널에서 숨김 파일을 확인하기 위해 `ls -al` 명령어를 입력했으나, `Get-ChildItem : 매개 변수 이름 'al'과(와) 일치하는 매개 변수를 찾을 수 없습니다.` 라는 에러가 발생함.
* **원인 가설:** 현재 열려있는 터미널이 Linux 환경이 아닌 Windows PowerShell(`PS`)로 설정되어 있어, Linux 전용 옵션인 `-al` 문법을 해석하지 못한 것으로 추정함.
* **확인 및 해결:** 
  1. PowerShell에서는 `ls -Force`를 사용해야 함을 확인함.
  2. 하지만 본 과제는 Linux CLI 환경 실습이 목적이므로, VS Code의 기본 터미널 프로필(Default Profile)을 `Git Bash`로 변경함.
  3. 새 터미널(Git Bash)을 열고 `ls -al`을 재입력한 결과, 정상적으로 숨김 파일 목록이 출력됨을 확인함.
