#
#  Author: Guido Schmutz
#  Date: 2021-03-18
#
#  https://github.com/trivadispf/docker-trino-cli
#
FROM alpine:latest

ENV DEBIAN_FRONTEND noninteractive

ENV TRINO_VERSION=353 \
    TRINO_CLI_HOME=/opt/trino-cli \
    TRINO_CLI_JAR=/opt/trino-cli/trino-cli-${TRINO_VERSION}-executable.jar

# Install Trino CLI
RUN mkdir -p "/opt/trino-cli" \
 && wget "https://repo1.maven.org/maven2/io/trino/trino-cli/${TRINO_VERSION}/trino-cli-${TRINO_VERSION}-executable.jar" \
      -q -O "$TRINO_CLI_JAR" \
 && chmod +x "$TRINO_CLI_JAR" \
 && ln -s "$TRINO_CLI_JAR" /usr/local/bin/trino \
 && apk update \
 && apk add less \
 && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

CMD ["trino"]