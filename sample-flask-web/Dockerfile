FROM python:2.7-alpine

RUN mkdir /app
WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

COPY . .

LABEL maintainer="Vinay K Vishwakarma"

CMD gunicorn -c gunicorn.py "hello.app:create_app()"
