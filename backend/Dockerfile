FROM python:3.9-slim


WORKDIR /app


COPY pyproject.toml poetry.loc ./
RUN pip install poetry && poetry install --no-root

COPY . .


CMD ["poetry", "run", "uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]

