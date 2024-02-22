FROM python:3.9

LABEL mainter="Peng"

WORKDIR /app

COPY ./requirements.txt /app/requirements.txt
RUN pip3 install -r requirements.txt

COPY ./auto.py /app/auto.py

CMD ["python3", "auto.py"]