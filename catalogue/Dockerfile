#FROM node:20
WORKDIR /opt/server
COPY package.json .
COPY server.js .
# by reading package.json dependencies is installed 
RUN npm install 
ENV mongo="true" \
    MONGO_URL="mongodb://Mongodb:27017/catalogue"
CMD ["node","server.js"]

 
