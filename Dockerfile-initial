FROM node:14.16.1

RUN mkdir /usr/src/goof
RUN mkdir /tmp/extracted_files
ADD . /usr/src/goof
RUN cd /usr/src/goof

RUN npm ci --only=production
EXPOSE 3001
EXPOSE 9229
ENTRYPOINT npm start
