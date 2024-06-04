FROM python:3.9

LABEL mainter="Peng"

WORKDIR /mutating

COPY ../requirements.txt /mutating/requirements.txt
RUN pip3 install -r requirements.txt

COPY ./webhook_server.py /mutating/webhook_server.py

CMD ["python3", "webhook_server.py"]