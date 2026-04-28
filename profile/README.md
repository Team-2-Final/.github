🚀 프로젝트 로컬 환경 세팅 가이드
진행 환경: VS Code 터미널 (Command Prompt 기준)

🎨 1. 프론트엔드 (Frontend)
레포지토리 클론

Bash
git clone https://github.com/Team-2-Final/Frontend.git
패키지 설치
VS Code 터미널에서 설치 경로로 이동 후 아래 명령어를 실행합니다.

Bash
npm install
작업 폴더로 이동

Bash
cd frontend
프로젝트 실행

Bash
npm start
💡 Tip: 실행이 안 될 경우, npm start를 입력했던 경로에서 npm install을 다시 실행해 보세요.

⚙️ 2. 백엔드 (Backend)
레포지토리 클론

Bash
git clone https://github.com/Team-2-Final/Backend.git
가상환경 생성 및 실행
VS Code 터미널에서 백엔드 설치 경로로 이동 후 가상환경을 세팅합니다.

Bash
python -m venv .venv
.venv\scripts\activate.bat
요구 패키지 설치

Bash
pip install -r requirements.txt
FastAPI 서버 실행

Bash
uvicorn app.main:app --reload
🔗 Swagger UI 주소: http://localhost:8000/docs

🗄️ 3. 데이터베이스 (Oracle DB)
📥 오라클 설치
버전: Oracle Database 21c Express Edition for Windows (64-bit)

다운로드 링크: Oracle 공식 홈페이지

👤 계정 및 권한 설정
CMD 창을 열고 아래 순서대로 명령어를 실행합니다.

설치 및 접속 확인 (1234는 설치 시 설정한 비밀번호)

Bash
sqlplus system/1234@localhost:1521/XEPDB1
계정 생성 및 권한 부여 (SQL 쉘 내부에서 실행)

SQL
-- 계정 생성
CREATE USER smart1234 IDENTIFIED BY farm1234;

-- 기본 권한 부여
GRANT CONNECT, RESOURCE TO smart1234;

-- 테이블스페이스 사용 권한 부여
ALTER USER smart1234 QUOTA UNLIMITED ON USERS;

-- 생성 확인 (smart1234가 출력되면 성공)
SELECT username FROM dba_users;
🛠️ DB 테이블 초기화
프로젝트 루트 경로에서 아래 스크립트를 실행하여 테이블을 세팅합니다.

Bash
# 테이블 초기 생성
sqlplus smart1234/farm1234@localhost:1521/XEPDB1 @app/db_init_.sql

# 문제 발생 시 테이블 리셋
sqlplus smart1234/farm1234@localhost:1521/XEPDB1 @app/db_reset.sql
🤖 4. 머신러닝 (ML / AI)
🧠 AI 모델 1
레포지토리 클론

Bash
git clone https://github.com/Team-2-Final/ML.git
가상환경 종료 (터미널 경로 앞에 .venv가 표시된 경우)

Bash
deactivate
요구 패키지 설치 및 실행

Bash
pip install -r requirements-api.txt
python -m serving
💡 Tip: 실행이 안 될 경우, requirements-ml.txt, requirements-dev.txt 등 다른 requirements 파일도 모두 설치해 본 후 다시 실행해 보세요.

🧠 AI 모델 2
레포지토리 클론 및 브랜치 전환

Bash
git clone https://github.com/Team-2-Final/ML.git
git checkout other
가상환경 종료 (터미널 경로 앞에 .venv가 표시된 경우)

Bash
deactivate
요구 패키지 설치 및 실행

Bash
pip install -r requirements.txt
python run.py
🕹️ 5. 시뮬레이터 실행 (Simulator)
각 시뮬레이터는 백엔드 파일 내부의 해당 폴더로 이동(cd)한 후 실행합니다.

일반 시뮬레이터 실행

Bash
cd simulator
python simulator1.py
이미지(CCTV) 시뮬레이터 실행

Bash
cd cctv_simulator
python cctv_simulator.py
