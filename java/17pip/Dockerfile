FROM        --platform=$TARGETOS/$TARGETARCH eclipse-temurin:17-jdk-jammy

LABEL       author="I'm Carsen" maintainer="carsen@imcarsen.com"

LABEL       org.opencontainers.image.source="https://github.com/imcarsen/yolks"
LABEL       org.opencontainers.image.licenses=MIT

RUN 		apt-get update -y \
 			&& apt-get install -y lsof curl ca-certificates openssl git tar sqlite3 fontconfig libfreetype6 tzdata iproute2 libstdc++6 python3 python3-pip \
			&& pip3 install jep alt-profanity-check \
 			&& useradd -d /home/container -m container
			

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]