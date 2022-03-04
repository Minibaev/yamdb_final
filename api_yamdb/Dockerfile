FROM python:3.7-slim

WORKDIR /app

COPY . ./

RUN pip3 install -r /app/requirements.txt --no-cache-dir

RUN cd api_yamdb/

RUN python3 manage.py migrate

RUN python3 manage.py collectstatic --noinput

RUN cp redoc.yaml static/

CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]