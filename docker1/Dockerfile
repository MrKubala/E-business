FROM ubuntu


RUN apt-get update
RUN apt-get install apt-transport-https -y

RUN apt-get install default-jdk -y

RUN apt-get install scala -y

RUN echo "deb https://dl.bintray.com/sbt/debian /" | tee -a /etc/apt/sources.list.d/sbt.list
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2EE0EA64E40A89B84B2DF73499E82A75642AC823
RUN apt-get update
RUN apt-get install sbt -y

RUN mkdir /app
WORKDIR /app

COPY ./build.sbt ./
RUN sbt update


CMD sbt console
