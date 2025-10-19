FROM python:3.11-slim

WORKDIR /app

# Устанавливаем зависимости для PostgreSQL
RUN apt-get update && apt-get install -y gcc libpq-dev && rm -rf /var/lib/apt/lists/*

# Обновляем pip и устанавливаем зависимости
RUN pip install --upgrade pip && pip install --no-cache-dir -r requirements.txt

# Копируем все файлы
COPY . .

# Запускаем приложение с динамическим портом от Railway
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "$PORT"]
