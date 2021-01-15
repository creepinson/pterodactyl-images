FROM        python:3.8-alpine

LABEL       author="Theo Paris" maintainer="theoparisdesigns@gmail.com"

RUN         apk add --no-cache --update curl bash \
    && adduser -D -h /home/container container

USER        container
ENV         USER=container HOME=/home/container

WORKDIR     /home/container

RUN curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python
ENV PATH = "${PATH}:${HOME}/.poetry/bin:${HOME}/.local/bin"
RUN pip install -U poethepoet

COPY        ./entrypoint.sh /entrypoint.sh

CMD         ["/bin/bash", "/entrypoint.sh"]
