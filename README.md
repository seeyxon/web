# 학사 관리 시스템 (University Academic Management System)


데이터베이스 응용 수업의 실습 프로젝트로 제작한 학사 관리 웹 애플리케이션입니다.  
Node.js와 Oracle DB를 활용하여 교수·학생·강좌 정보를 관리하고 게시판 기능을 제공합니다.

## 기술 스택

| 분류 | 기술 |
|------|------|
| Runtime | Node.js |
| Framework | Express.js |
| Template Engine | EJS |
| Database | Oracle DB (XE) |
| Driver | oracledb |

## 주요 기능

### 교수 관리 `/haksa/pro`
- 교수 목록 조회 (코드, 이름, 학과, 직위, 급여, 임용일)
- 교수 등록
- 교수 삭제

### 학생 관리 `/haksa/stu`
- 학생 목록 조회 (학번, 이름, 학과, 생년월일, 학년, 지도교수)
- 학생 등록
- 학생 삭제

### 강좌 관리 `/haksa/cou`
- 강좌 목록 조회 (강좌코드, 강좌명, 시간, 강의실, 담당교수, 정원, 수강인원)

### 게시판 `/posts`
- 게시글 목록 조회 (페이지네이션)
- 게시글 작성 / 조회 / 수정 / 삭제

## 프로젝트 구조

```
web/
├── app.js              # 앱 진입점
├── connect.js          # Oracle DB 연결 설정
├── routes/
│   ├── index.js        # 메인 라우터
│   ├── haksa.js        # 교수·학생·강좌 라우터
│   ├── posts.js        # 게시판 라우터
│   └── users.js        # 사용자 라우터
├── views/
│   ├── index.ejs       # 레이아웃
│   ├── haksa/          # 학사 관련 뷰
│   └── posts/          # 게시판 관련 뷰
└── public/             # 정적 파일 (CSS, JS)
```

## 실행 방법

### 사전 요구사항
- Node.js 설치
- Oracle DB XE 설치 및 실행

### DB 설정

`connect.js`에서 Oracle DB 접속 정보를 환경에 맞게 수정하세요.

```js
connection = await oracledb.getConnection({
    user: 'user01',
    password: '1234',
    connectionString: 'localhost/xe'
});
```

### 설치 및 실행

```bash
# 패키지 설치
npm install

# 서버 실행
npm start
```

서버 실행 후 `http://localhost:3000` 에서 접속할 수 있습니다.
