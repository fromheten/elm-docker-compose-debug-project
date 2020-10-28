FROM ubuntu

RUN apt-get update -y && apt-get upgrade -y && apt-get install -y wget

RUN TZ=Etc/UTC ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y nodejs npm

WORKDIR /build

ADD . .

RUN npm install

ENTRYPOINT ./node_modules/.bin/elm
