깃으로 받아서 세팅법(vscode 기준, 터미널 command prompt)

프론트
1. 깃에서 git clone (https://github.com/Team-2-Final/Frontend.git)
2. vscode 터미널에서 해당 설치 경로까지 들어가서 
   npm install
3. 이후 터미널에서
   cd frontend 입력해서 이동
4. npm start 
   안될 시
   npm start 했던 경로에서 다시 npm install


백엔드
1. 깃에서 git clone (https://github.com/Team-2-Final/Backend.git)
2. vscode 터미널에서 해당 설치 경로까지 들어가서 백엔드용 환경 생성
3. python -m venv .venv       = 가상환경 폴더 생성
4. .venv\scripts\activate.bat  = 가상환경 실행
5. pip install -r requirements.txt  = 가상환경 요구 패키지 설치
6. 이후 fastapi 실행
   uvicorn app.main:app --reload

fastapi 스웨거 주소
localhost:8000/docs


db 설정
오라클 설치
https://www.oracle.com/kr/database/technologies/xe-downloads.html
Oracle Database 21c Express Edition for Windows (64-bit)

오라클 계정 생성
id : smart1234
pwd : farm1234

cmd 명령어 순서

설치 확인
sqlplus system/1234@localhost:1521/XEPDB1
(1234는 설치시 설정한 비밀번호)실행 확인 후 sql 내부에서

계정 생성
CREATE USER smart1234 IDENTIFIED BY farm1234;

권한 부여
GRANT CONNECT, RESOURCE TO smart1234;

테이블 사용 권한 부여
ALTER USER smart1234 QUOTA UNLIMITED ON USERS;

생성 확인
SELECT username FROM dba_users;
smart1234 확인


db 테이블 초기 설정법
프로젝트 경로에서
sqlplus smart1234/farm1234@localhost:1521/XEPDB1 @app/db_init_.sql

문제 생겨서 테이블 제대로 생성 안됐을 때 리셋 명령
sqlplus smart1234/farm1234@localhost:1521/XEPDB1 @app/db_reset.sql



ml ai1
1. 깃에서 git clone (https://github.com/Team-2-Final/ML.git)
2. 설치 경로에서 pip install -r requirements-api.txt
3. python -m serving
   안될 시 2번 과정의 requirements라 이름 붙은 ml, dev 다 설치해보고 다시 실행

ml2 ai2
1. 깃에서 git clone (https://github.com/Team-2-Final/ML.git) + git checkout other 명령으로 ai2로 전환
2. 설치 경로에서 pip install -r requirements.txt
3. python run.py



시뮬 실행법(환경)
백엔드 파일 내부의 simulator폴더까지 이동(cd) 후 python simulator1.py

이미지 시뮬 
백엔드 cctv_simulator 폴더까지 이동(cd) 후 python cctv_simulator.py
