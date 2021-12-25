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

#RUN apk add libexecinfo

CMD python3 ./example.py
