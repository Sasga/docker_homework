FROM python:3.9.11-alpine3.15

WORKDIR /app

RUN apk add --update --no-cache bash g++ gcc libxml2-dev libxslt-dev python3-dev postgresql-dev curl

COPY requirements.txt .

RUN pip install -r requirements.txt

COPY . .

EXPOSE 8000

ENTRYPOINT ["./docker-entrypoint.sh"]
