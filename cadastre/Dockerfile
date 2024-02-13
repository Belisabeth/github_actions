#FROM node:16-alpine
FROM node:16
#RUN sudo apt-get install bash

RUN mkdir -p /app
WORKDIR /app

RUN mkdir -p sources sources-edigeo sources-dxf-cc dist 

#COPY *.sh ./
COPY cadastre_sh\*.sh ./
COPY package.json ./

RUN npm install --global --force yarn
RUN yarn global add @etalab/cadastre

RUN chmod 777 /app/sources-edigeo -R
RUN chmod 777 /app/sources-dxf-cc -R
RUN chmod 777 /app/dist


USER node
CMD ["npm", "run", "start"]

ENTRYPOINT ["/bin/bash"]
#ENTRYPOINT ["npm start"]
