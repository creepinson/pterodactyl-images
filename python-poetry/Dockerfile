FROM        python:3.8-alpine

LABEL       author="Theo Paris" maintainer="theoparisdesigns@gmail.com"

RUN         apk add --no-cache --update \
            && adduser -D -h /home/container container

RUN curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python
ENV PATH = "${PATH}:/root/.poetry/bin"
RUN pip install poetry poethepoet

USER        container
ENV         USER=container HOME=/home/container

WORKDIR     /home/container

COPY        ./entrypoint.sh /entrypoint.sh

CMD         ["/bin/ash", "/entrypoint.sh"]
