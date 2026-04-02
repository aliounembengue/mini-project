FROM python:3.13-slim

LABEL maintainer="Alioune Badara Mbengue"

COPY requirements.txt /
COPY student_age.py /

RUN apt-get update && \
    apt-get install -y \
    python3-dev \
    libsasl2-dev \
    libldap2-dev \
    libssl-dev \
    gcc \
    && rm -rf /var/lib/apt/lists/*

RUN pip3 install -r /requirements.txt

RUN mkdir /data

COPY student_age.json /data/student_age.json

VOLUME /data

EXPOSE 5000

CMD ["python3", "./student_age.py"]
