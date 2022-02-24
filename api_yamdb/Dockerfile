FROM python:3.7-slim

RUN apt-get update \
    && apt-get -y install libpq-dev gcc

WORKDIR /app

COPY api_yamdb/requirements.txt ./

RUN pip3 install -r ./requirements.txt --no-cache-dir

COPY api_yamdb ./
COPY tests ./tests
COPY yamdb_workflow.yml ./

# Выполнить запуск сервера разработки при старте контейнера.
CMD [ "sh", "-c", \
"python3 manage.py migrate \
&& \
python3 manage.py collectstatic --noinput \
&& \
cp redoc.yaml static/ \
&& \
gunicorn api_yamdb.wsgi:application --bind 0:8000" \
]