FROM python:3.8
RUN python -m venv /app/venv
WORKDIR /app
COPY . .
RUN . /app/venv/bin/activate && pip install --upgrade pip && pip install -r requirements.txt
EXPOSE 8000
CMD . /app/venv/bin/activate && python manage.py migrate && python manage.py runserver 0.0.0.0:8000
