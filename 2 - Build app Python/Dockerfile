FROM python:3.6
LABEL maintainer 'Meu nome'

RUN useradd www && \
    mkdir /app && \
    mkdir /log && \
    chown www /log

USER www
VOLUME /log
WORKDIR /app
EXPOSE 8888

ENTRYPOINT ["/usr/local/bin/python"]
CMD ["run.py"]