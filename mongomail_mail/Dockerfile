FROM ubuntu:16.04

RUN apt-get update &&\
    apt-get -y install python3 python3-pip git

RUN git clone https://github.com/terrabitz/MongoMail /app
RUN pip3 install -r /app/requirements.txt
ENV PYTHONPATH="/app"
RUN rm /app/mongomail/config.py
COPY ./docker-config.py /app/mongomail/config.py

ENTRYPOINT ["python3", "/app/mongomail/run_mail.py"]