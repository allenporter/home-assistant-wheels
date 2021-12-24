ARG BUILD_FROM
FROM ${BUILD_FROM}

ARG WHEEL
ENV PIP_WHEEL=${WHEEL}

RUN python3 --version

WORKDIR /code
COPY example.py .
COPY ${PIP_WHEEL} .

RUN pip3 install --upgrade pip
RUN python3 -m pip debug --verbose
RUN pip3 install $PIP_WHEEL
RUN pip3 install google-cloud-pubsub

#RUN pip3 install Cython
RUN apk add libc6-compat libstdc++ libatomic musl-dev
#RUN apk add gcompat
#RUN apk add python3-dev
#RUN apk add libc6-compat
#RUN apk add build-base cmake git linux-headers libexecinfo-dev bluez-dev libffi-dev openssl-dev glib-dev eudev-dev libxml2-dev libxslt-dev libpng-dev libjpeg-turbo-dev tiff-dev autoconf automake cups-dev gmp-dev mpfr-dev mpc1-dev ffmpeg-dev gammu-dev cargo

CMD python3 ./example.py
