FROM debian:wheezy
MAINTAINER Owen Change <tobeand@gmail.com>


RUN echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu precise main" | tee /etc/apt/sources.list.d/webupd8team-java.list
RUN echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu precise main" | tee -a /etc/apt/sources.list.d/webupd8team-java.list
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys EEA14886
RUN apt-get update

RUN echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections
RUN apt-get -y install oracle-java7-installer ant && apt-get clean
RUN echo "JAVA_HOME=/usr/lib/jvm/java-7-oracle" >> /etc/environment

RUN apt-get -y install unzip

ADD http://jaist.dl.sourceforge.net/project/pentaho/Data%20Integration/5.1/pdi-ce-5.1.0.0-752.zip / 
RUN unzip pdi-ce-5.1.0.0-752.zip

WORKDIR /data-integration

EXPOSE 8181

CMD ["./carte.sh", "0.0.0.0", "8181"]



