FROM node:6-alpine

EXPOSE 3000

RUN  add --no-cache tini

WORKDIR /usr/src/

COPY package

RUN npm install &&

COPY . .

CMD [ "/sbin/tini", "--", "node",

