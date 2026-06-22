FROM python:3.12

WORKDIR /app

# Сначала ставим системную зависимость gunicorn (она закешируется)
RUN pip install gunicorn==25.3.0

COPY requirements.txt .

RUN pip install -r requirements.txt --no-cache-dir

COPY . .

# Меняем команду старта: теперь запускаем через gunicorn на порту 8000
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]
