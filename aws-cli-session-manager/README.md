# aws-cli-session-manager

Add a [Session Manager plugin](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-working-with-install-plugin.html) into [official AWS CLI image](https://hub.docker.com/r/amazon/aws-cli).

## Build an image

```
docker build . --build-arg AWS_CLI_VERSION=<AWS-CLI-version> -t mazemaze567/aws-cli-session-manager:<AWS-CLI-version>
```

build-args (default):
- `AWS_CLI_VERSION`: `latest`

## Usage

The same usage as the official image. (See: https://hub.docker.com/r/amazon/aws-cli)

Set alias:

```sh
alias aws='docker run --rm -ti -v ~/.aws:/root/.aws -v $(pwd):/aws mazemaze567/aws-cli-session-manager:latest'
```

Check AWS CLI version

```sh
aws --version
```

And, use Session Manager:
```sh
aws ssm start-session --target <your-instance-id>
```

