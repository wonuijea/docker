# 수강기록 API (FastAPI)

FastAPI를 이용한 수강기록 REST API 서버입니다.

## 실행 방법

### 1. 패키지 설치

```bash
pip install -r requirements.txt
```

### 2. 서버 실행

```bash
uvicorn main:app --reload
```

서버가 실행되면 `http://127.0.0.1:8000` 에서 접근할 수 있습니다.

---

## API 엔드포인트

### GET `/courses`

전체 수강기록을 반환합니다.

**요청 예시 (Postman)**
- Method: `GET`
- URL: `http://127.0.0.1:8000/courses`

**응답 예시**
```json
[
  {
    "course_name": "자료구조",
    "year": "2025",
    "semester": "2",
    "grade": "A+"
  }
]
```

---

### POST `/courses`

새로운 수강기록을 추가합니다.

**요청 예시 (Postman)**
- Method: `POST`
- URL: `http://127.0.0.1:8000/courses`
- Body (raw / JSON):

```json
{
  "course_name": "인간로봇상호작용",
  "year": "2026",
  "semester": "2",
  "grade": "A+"
}
```

**응답 예시**
```json
{
  "message": "과목이 추가되었습니다.",
  "course": {
    "course_name": "인간로봇상호작용",
    "year": "2026",
    "semester": "2",
    "grade": "A+"
  }
}
```

---

## 프로젝트 구조

```
.
├── main.py          # FastAPI 서버 코드
├── courses.json     # 수강기록 데이터 파일
├── requirements.txt # 필요 패키지 목록
├── .gitignore
└── README.md
```

---

## 자동 API 문서

서버 실행 후 아래 주소에서 Swagger UI를 확인할 수 있습니다:

- http://127.0.0.1:8000/docs