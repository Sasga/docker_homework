FROM python:3.9.11-alpine3.15

WORKDIR /app

RUN apk add --update --no-cache g++ gcc bash libxml2-dev libxslt-dev postgresql-dev python3-dev musl-dev 

COPY requirements.txt .

RUN pip install -r requirements.txt

COPY . .

ENTRYPOINT ["./docker-entrypoint.sh"]
