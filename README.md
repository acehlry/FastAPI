# FastAPI

```sh
# 설치
pip install fastapi

# 프로덕션용 ASGI 서버 Uvicorn
pip install "uvicorn[standard]"
```

## 예제 파일 생성

```py
from typing import Union

from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"Hello": "World"}

@app.get("/items/{item_id}")
def read_item(item_id: int, q: Union[str, None] = None):
    return {"item_id": item_id, "q":q}
```

## 실행

```sh
uvicorn main:app --reload
```

※uvicorn 명령어가 안될 경우

-   설정파일에서 경로 등 기초 설정 추가

1. 응답확인

http://127.0.0.1:8000/items/5?q=somequery

2. Swagger, API 문서 확인

http://127.0.0.1:8000/docs
http://127.0.0.1:8000/redoc
