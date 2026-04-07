FROM python:3.12-slim

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1
ENV STREAMLIT_SERVER_HEADLESS=true

WORKDIR /app

COPY pyproject.toml README.md ./
COPY src ./src
COPY app.py ./app.py

RUN pip install --no-cache-dir --upgrade pip \
    && pip install --no-cache-dir ".[dashboard]"

EXPOSE 8501

CMD ["sh", "-c", "streamlit run app.py --server.address 0.0.0.0 --server.port ${PORT:-8501} --server.headless true"]

