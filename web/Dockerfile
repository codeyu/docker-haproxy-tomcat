FROM codeyu/ubuntu-openjdk:8
# Creator info
MAINTAINER zhu yu <codeyu@gmail.com>

# Install dependencies
RUN apt-get update && \
RUN apt-get install -y wget tar && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Define commonly used JAVA_HOME variable
ENV CATALINA_HOME /usr/local/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH
RUN mkdir -p "$CATALINA_HOME"
WORKDIR $CATALINA_HOME

ENV TOMCAT_MAJOR 8
ENV TOMCAT_VERSION 8.5.15
ENV TOMCAT_TGZ_URL http://mirror.bit.edu.cn/apache/tomcat/tomcat-$TOMCAT_MAJOR/v$TOMCAT_VERSION/bin/apache-tomcat-$TOMCAT_VERSION.tar.gz
# Get Tomcat
RUN wget --no-cookies $TOMCAT_TGZ_URL  -O tomcat.tar.gz && \
    tar -xvf tomcat.tar.gz --strip-components=1 && \
    rm bin/*.bat && \
    rm tomcat.tar.gz* && \
    rm -rf webapps/examples && \
    rm -rf webapps/docs && \
    rm -rf webapps/manager && \
    rm -rf webapps/host-manager && \
    rm -rf webapps/ROOT/*
ADD index.html webapps/ROOT
EXPOSE 8080

# Launch Tomcat
CMD ["bin/catalina.sh", "run"]