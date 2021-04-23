# aws-cdk-cli-python

This image is for using AWS CDK CLI with Python development.


## Build an image

```
docker build . --build-arg AWS_CDK_VERSION=<AWS-CDK-version> -t mazemaze567/aws-cdk-cli-python:<AWS-CDK-version>
```

build-args (default):
- `BASE_PYTHON_VERSION`: `3.8.6`
- `NODE_VERSION`: `14.14.0`
- `PIP_PIPENV_VERSION`: `2020.11.15`
- `AWS_CDK_VERSION`: `latest`


## Usage

### Run a container

```sh
docker run --rm \
  -v ~/.aws:/root/.aws \
  -v $(pwd):/cdk \
  -it \
  mazemaze567/aws-cdk-cli-python:<AWS-CDK-version> '/bin/bash'
```

### Init (in the container)

Initialize CDK:

```sh
cdk init app --language=python --generate-only
```

Initialize Pipenv:

```sh
pipenv install --python 3.8.6
```

### Check (in the container)

Enable pipenv environment:

```sh
pipenv shell
```

Check CDK CLI version:

```sh
cdk --version
```

Synthesize CDK sample app:

```sh
cdk synth
```


Now you can develop your CDK app.

