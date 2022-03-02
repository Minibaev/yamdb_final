FROM python:3.7-slim

WORKDIR /app

COPY . ./

RUN pip3 install -r /app/requirements.txt --no-cache-dir

CMD [ "sh", "-c", \
"python3 manage.py migrate \
&& \
python3 manage.py collectstatic --noinput \
&& \
cp redoc.yaml static/ \
&& \
gunicorn api_yamdb.wsgi:application --bind 0:8000" \
]