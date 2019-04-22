FROM mats16/mecab-python3:0.996

LABEL maintainer "mats116 <mats.kazuki@gmail.com>"

COPY mecabrc /usr/local/etc/mecabrc

RUN apk add --no-cache --virtual=build-deps git bash curl file openssl sudo perl

ONBUILD RUN git clone --depth 1 https://github.com/neologd/mecab-ipadic-neologd.git /tmp/neologd && \
            /tmp/neologd/bin/install-mecab-ipadic-neologd -n -y && \
            apk del build-deps && \
            rm -rf /tmp/neologd
