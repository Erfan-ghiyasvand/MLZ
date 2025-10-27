FROM agrigorev/zoomcamp-model:2025

WORKDIR /app

RUN pip install uv

COPY pyproject.toml uv.lock ./

RUN uv sync --frozen

COPY predict.py .
COPY pipeline_v1.bin .

EXPOSE 8000

CMD ["uv", "run", "uvicorn", "predict:app", "--host=0.0.0.0", "--port=8000"]