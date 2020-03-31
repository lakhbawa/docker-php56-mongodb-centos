FROM mongo:latest

#RUN apt-get update && apt-get install apt-file -y && apt-file update && apt-get install vim -y 

COPY ./.docker/mongo/mongo.conf /etc/mongo.conf
#RUN rm /tmp/mongodb-27017.sock

CMD mongod