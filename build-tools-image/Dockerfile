FROM maven:3.8.6-openjdk-11
RUN apt-get update && apt-get install -y \
            autoconf \
            automake \
            zsh \
            xmlstarlet \
            unzip \
            python3 \
            python3-venv \
            git \
            jq \
            make

RUN curl "https://s3.amazonaws.com/aws-cli/awscli-bundle.zip" -o "awscli-bundle.zip"
RUN unzip awscli-bundle.zip
RUN python3 ./awscli-bundle/install -i /usr/local/aws -b /usr/local/bin/aws && rm -rf ./awscli-bundle/install
RUN curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
RUN chmod +x /usr/local/bin/docker-compose
RUN apt install docker.io -y
RUN mkdir -p /mnt/code
WORKDIR /mnt/code
