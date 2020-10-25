ARG AWS_CLI_VERSION=latest
FROM amazon/aws-cli:$AWS_CLI_VERSION

RUN curl "https://s3.amazonaws.com/session-manager-downloads/plugin/latest/linux_64bit/session-manager-plugin.rpm" -o "session-manager-plugin.rpm" \
  && yum install -y session-manager-plugin.rpm \
  && rm -f "session-manager-plugin.rpm"

