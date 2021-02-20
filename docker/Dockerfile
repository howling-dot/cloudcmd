FROM node
LABEL maintainer="Coderaiser"

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY package.json /usr/src/app/

RUN npm config set package-lock false && \
    npm install --production && \
    npm i gritty && \
    npm cache clean --force

COPY . /usr/src/app

WORKDIR /

ENV cloudcmd_terminal false
ENV cloudcmd_terminal_path gritty
ENV cloudcmd_open false
ENV cloudcmd_auth true
ENV cloudcmd_username admin
ENV cloudcmd_password 07110711

EXPOSE 8000

ENTRYPOINT ["/usr/src/app/bin/cloudcmd.mjs"]

