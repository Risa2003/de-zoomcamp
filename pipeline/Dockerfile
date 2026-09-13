FROM python:3.13.11-slim
RUN pip install pandas pyarrow
COPY --from=ghcr.io/astral-sh/uv:latest /uv /bin/
WORKDIR /code
COPY pyproject.toml uv.lock .python-version ./
RUN uv sync --frozen --no-install-project 
COPY pipeline.py .
ENTRYPOINT ["python","pipeline.py"]