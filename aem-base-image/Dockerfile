# Using 'centos:latest' (8) as the base image here
FROM centos:latest

#
MAINTAINER David Parker <dfparker@aemintegrators.com>

# Define variables.
ENV TZ America/Los_Angeles

# setting the working directory
WORKDIR /opt/aem

# Copy the license file
COPY license.properties .

# Copy Quickstart jar file
COPY cq-quickstart-6.5.0.jar cq-quickstart.jar

# Install Java
RUN yum update -y && \
    yum install -y curl && \
    yum install -y java-1.8.0-openjdk && \
    yum install -y vi

ENV JAVA_HOME /etc/alternatives/jre


# Unack the Jar file
RUN java -jar cq-quickstart.jar -unpack
RUN mkdir -p /opt/aem/crx-quickstart/install
RUN mkdir -p /opt/aem/crx-quickstart/logs
COPY install /opt/aem/crx-quickstart/

# MOUNT VOLUME
VOLUME ["/opt/aem/crx-quickstart/logs"]