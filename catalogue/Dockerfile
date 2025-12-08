FROM node:20.19.5-alpine3.22 AS build 
WORKDIR /opt/server
COPY package.json .
COPY  *.js .
# by reading package.json dependencies is installed 
RUN npm install 


FROM node:20.19.5-alpine3.22
WORKDIR /opt/server
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop && \ 
    chown -R roboshop:roboshop /opt/server
EXPOSE 8080
LABEL com.project="roboshop" \
      component="catalogue" \
      created_by="sivakumar"
ENV mongo="true" \
    MONGO_URL="mongodb://Mongodb:27017/catalogue"
COPY --from=build --chown=roboshop:roboshop /opt/server /opt/server
USER roboshop
CMD ["server.js"]
ENTRYPOINT ["node"]




# FROM node:20
# WORKDIR /opt/server
# COPY package.json .
# COPY server.js .
# # by reading package.json dependencies is installed 
# RUN npm install 
# ENV mongo="true" \
#     MONGO_URL="mongodb://Mongodb:27017/catalogue"
# CMD ["node","server.js"]

 
