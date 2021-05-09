FROM node:10-alpine

EXPOSE 3000

WORKDIR /usr/src/app

COPY package.json package-lock.json* ./
COPY .bash_profile .

RUN npm install && npm cache clean --force
RUN npm install axios chalk morgan helmet ejs
RUN npm install --save-dev nodemon
RUN apk add --update curl
RUN apk add --update vim
RUN apk add bash build-base curl file git gzip libc6-compat ncurses ruby ruby-dbm ruby-etc ruby-irb ruby-json sudo
RUN apk add --update nano
RUN apk add --update bash
RUN apk add bash-doc
RUN apk add bash-completion

RUN echo '\
        . /etc/profile ; \
    ' >> /root/.profile

COPY . .

CMD [ "node", "./bin/www" ]
