FROM python:3.10-slim
RUN pip install pipenv
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && \
    apt-get install -y libgdal-dev libmariadb3 &&\
    apt-get clean && \
    rm -rf /var/lib/apt/lists*
WORKDIR /code_be
COPY requirements.txt .
RUN  pip install -r requirements.txt

COPY . .
RUN python /code_be/manage.py collectstatic --noinput
