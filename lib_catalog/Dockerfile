FROM python:3.9.11-alpine3.15 as builder

WORKDIR /app

RUN apk add --update --no-cache bash g++ gcc libxml2-dev libxslt-dev python3-dev postgresql-dev curl

RUN python -m venv /opt/venv

ENV PATH="/opt/venv/bin:$PATH"

COPY requirements.txt .

RUN pip install -r requirements.txt

FROM python:3.9.11-alpine3.15

RUN apk add --update --no-cache bash curl postgresql-dev

COPY --from=builder /opt/venv /opt/venv

WORKDIR /app

ENV PATH="/opt/venv/bin:$PATH"

COPY . .

EXPOSE 8000

ENTRYPOINT ["./docker-entrypoint.sh"]
