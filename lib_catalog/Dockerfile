FROM python:3.9.11-alpine3.15

WORKDIR /

RUN apk add --update --no-cache g++ gcc libxml2-dev libxslt-dev postgresql-dev python3-dev musl-dev 
RUN pip install psycopg2-binary

COPY . .

RUN pip install -r requirements.txt

ENTRYPOINT ["python", "manage.py"]
