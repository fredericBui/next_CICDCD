# FROM jenkins/inbound-agent
# USER root
# RUN apt update && apt install -y curl
# RUN curl -fsSL https://deb.nodesource.com/setup_18.x | bash - \
#     && apt install -y nodejs
# RUN node -v && npm -v  
# RUN npm install -g next
# USER jenkins
# WORKDIR /home/jenkins/agent

FROM jenkins/inbound-agent
USER root
RUN apt update && apt install -y curl gnupg lsb-release ca-certificates
RUN curl -fsSL https://deb.nodesource.com/setup_18.x | bash - \
    && apt install -y nodejs
RUN node -v && npm -v
RUN npm install -g next
RUN curl -fsSL https://get.docker.com -o get-docker.sh && sh get-docker.sh
RUN sh get-docker.sh
USER jenkins
WORKDIR /home/jenkins/agent

