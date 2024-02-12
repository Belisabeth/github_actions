FROM node:16-alpine
RUN apk update && apk add bash
#RUN rm -r node_modules/@next/swc-linux-x64-gnu
RUN npm install --global --force yarn
RUN yarn global add @etalab/cadastre

RUN mkdir -p /app
WORKDIR /app

RUN mkdir -p sources sources-edigeo sources-dxf-cc dist 


COPY *.sh ./

RUN chmod 777 /app/sources-edigeo -R
RUN chmod 777 /app/sources-dxf-cc -R
RUN chmod 777 /app/dist


USER node

ENTRYPOINT ["/bin/bash"]
