FROM tiangolo/uwsgi-nginx-flask:flask-python3.5

RUN apt-get update &&\
    apt-get -y install git

RUN rm -rf /app/
RUN git clone https://github.com/terrabitz/MongoMail /app
RUN rm /app/mongomail/config.py
COPY ./docker-config.py /app/mongomail/config.py
COPY ./uwsgi.ini /app/uwsgi.ini
RUN pip3 install -r /app/requirements.txt
ENV PYTHONPATH="/app"

