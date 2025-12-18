FROM nvidia/cuda:12.4.1-cudnn9-runtime-ubuntu22.04

# 작업 디렉토리
WORKDIR /app

# 의존성 먼저 복사
COPY requirements.txt .

# 파이썬 라이브러리 설치(이미 설치된 라이브러리는 자동으로 스킵)
RUN pip install --no-cache-dir -r requirements.txt

# 앱 코드 복사
COPY app app

# FastAPI 내부 포트
EXPOSE 8000

# FastAPI 실행
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]