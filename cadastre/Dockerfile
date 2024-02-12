FROM node:16-bullseye
RUN npm install --global yarn
RUN yarn global add @etalab/cadastre
#RUN apt-get install --no-install-recommends -y \
#        bash \
#        curl \
#        msmtp \
#        nano \
#        rename \
#  && apt-get install -y unrar-free \
#    && apt-get clean \
#    && rm -rf /var/lib/apt/lists/*
#COPY msmtprc /etc/msmtprc

#RUN ln -sf /usr/bin/msmtp /usr/sbin/sendmail
#ENV TZ Europe/Berlin
#RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN mkdir -p /app
WORKDIR /app

#RUN groupadd -g 2001 osca && useradd -u2001 -g osca osca

RUN mkdir -p sources sources-edigeo sources-dxf-cc dist 

COPY import ./

RUN chmod 777 /app/sources-edigeo -R
RUN chmod 777 /app/sources-dxf-cc -R
RUN chmod 777 /app/dist


#USER osca

ENTRYPOINT ["/bin/bash"]
