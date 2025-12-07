FROM node:20.19.5-alpine3.22 as build 
WORKDIR /opt/server
COPY package.json .
COPY server.js .
# by reading package.json dependencies is installed 
RUN npm install 


FROM node:20.19.5-alpine3.22
WORKDIR /opt/server
COPY --from=build /opt/server /opt/server
ENV mongo="true" \
    MONGO_URL="mongodb://Mongodb:27017/catalogue"
CMD ["node","server.js"]




# FROM node:20
# WORKDIR /opt/server
# COPY package.json .
# COPY server.js .
# # by reading package.json dependencies is installed 
# RUN npm install 
# ENV mongo="true" \
#     MONGO_URL="mongodb://Mongodb:27017/catalogue"
# CMD ["node","server.js"]

 
