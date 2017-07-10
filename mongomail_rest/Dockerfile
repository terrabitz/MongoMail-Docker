FROM tiangolo/uwsgi-nginx-flask:flask-python3.5

RUN apt-get update &&\
    apt-get -y install git

RUN rm /app/uwsgi.ini
RUN git clone https://github.com/terrabitz/MongoMail /tmp/mongomail && \
    cp -R /tmp/mongomail/* /app/
RUN pip3 install -r /app/requirements.txt
ENV PYTHONPATH="/app"
RUN rm /app/mongomail/config.py && \
    rm /app/main.py
COPY ./docker-config.py /app/mongomail/config.py
