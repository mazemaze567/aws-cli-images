ARG BASE_PYTHON_VERSION=3.8.6
FROM python:${BASE_PYTHON_VERSION}-slim-buster

# node, npm, ...
ARG NODE_VERSION=14.14.0
RUN set -eux \
    && apt-get update \
    && apt-get install -y npm curl git \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && npm i -g n \
    && n ${NODE_VERSION} \
    && apt-get purge -y nodejs npm \
    && apt-get clean

# Pipenv
ARG PIP_PIPENV_VERSION=2020.8.13
RUN pip install pipenv==${PIP_PIPENV_VERSION}
ENV PIPENV_VENV_IN_PROJECT=1

# AWS CDK CLI
ARG AWS_CDK_VERSION=latest
RUN set -eux \
    && npm i -g aws-cdk@${AWS_CDK_VERSION}

WORKDIR /cdk

