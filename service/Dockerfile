FROM python:3.6.6

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        postgresql-client \
    && rm -rf /var/lib/apt/lists/*

# RUN virtualenv . && . bin/activate
WORKDIR /app

COPY ./src /app

COPY ./requirements /requirements

RUN pip install -U pip && pip install --no-cache-dir -r /requirements/base.pip

CMD [ "python", "manage.py", "runserver", "0.0.0.0:80", "--settings=src.settings.dev" ]