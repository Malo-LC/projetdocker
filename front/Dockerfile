FROM ubuntu:16.04

# Update and upgrade ubuntu
RUN apt-get update &&\
	apt-get upgrade
	
#Installation of curl
RUN apt-get -y install curl net-tools

# Get JDK-11, extract and move into opt directory
RUN curl -o  openjdk-11.0.2_linux-x64_bin.tar.gz "https://download.java.net/java/GA/jdk11/9/GPL/openjdk-11.0.2_linux-x64_bin.tar.gz" &&\
	tar xvf openjdk-11.0.2_linux-x64_bin.tar.gz &&\
	mv jdk-11.0.2 /opt/

# Set JAVA_HOME environnement variable	
ENV JAVA_HOME=/opt/jdk-11.0.2
RUN export JAVA_HOME
ENV PATH=$PATH:$JAVA_HOME/bin
RUN export PATH 

# Add java program to the container
ADD ProgApp.jar .

# Add the script to run the java program
RUN echo 'java -jar ProgApp.jar' >> /startup.sh

# Launch the start script of our application
ENTRYPOINT ["sh", "/startup.sh"]

# Expose the port of our application
EXPOSE 8080