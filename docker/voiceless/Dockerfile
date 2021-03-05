FROM python:3.7-slim

ARG DEBIAN_FRONTEND=noninteractive
ARG ASKBOB_SETUP_CONFIG=.

RUN apt update && apt install -y build-essential git

WORKDIR /askbob

WORKDIR /askbob/installation
RUN git clone https://github.com/UCL-COMP0016-2020-Team-39/AskBob
WORKDIR /askbob/installation/AskBob

RUN rm -rf plugins
RUN python -m pip install -U pip setuptools wheel
RUN python -m pip install -e .
RUN python -m spacy download en_core_web_md

WORKDIR /askbob/build

RUN mkdir data

COPY ./plugins plugins
COPY ./*.ini .
COPY ./*.json .
COPY ./data data

RUN python -m askbob --setup $ASKBOB_SETUP_CONFIG

ENTRYPOINT python -m askbob -s

EXPOSE 8000
