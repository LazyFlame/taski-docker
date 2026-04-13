FROM python:3.12

WORKDIR /app

# Системная зависимость (веб-сервер)
RUN pip install gunicorn==23.0.0

# Зависимости приложения
COPY requirements.txt .
RUN pip install -r requirements.txt --no-cache-dir

# Копируем проект
COPY . .

# Запуск через Gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]


