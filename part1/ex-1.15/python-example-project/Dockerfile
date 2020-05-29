FROM python:3.7

WORKDIR /work

COPY . .

EXPOSE 8888

RUN pip install pipenv \
    && pipenv install

ENTRYPOINT [ "pipenv" ]
CMD ["run", "python", "main.py"]