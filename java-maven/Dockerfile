#docker build -t java_maven .
#Dockerfile构建依赖于宿主机的jdk于maven环境
#which java -> ~/Documents/docker_env/jdk1.8.0_181
#which mvn -> ~/Documents/docker_env/apache-maven-3.5.4
#docker run -d -v ~/Documents/docker_env/jdk1.8.0_181:/usr/local/jdk -v ~/Documents/docker_env/apache-maven-3.5.4:/usr/local/maven --name java_maven java_maven
FROM centos

ENV JAVA_HOME=/usr/local/jdk
ENV CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV MAVEN_HOME /usr/local/maven
ENV PATH $PATH:$JAVA_HOME/bin:$MAVEN_HOME/bin

CMD ["java", "-version"]
CMD ["mvn", "-v"]