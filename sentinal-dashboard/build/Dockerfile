FROM openjdk:8-jre-alpine
MAINTAINER pader "foreveryang321@gmail.com"

ENV APP_NAME="sentinel-dashboard" \
    SENTINEL_DASHBOARD_SERVER="localhost:8848" \
    SENTINEL_LOG_DIR="/logs/${APP_NAME}" \
    SENTINEL_METRIC_FILE_SINGLE_SIZE="52428800" \
    SENTINEL_METRIC_FILE_TOTAL_COUNT="6" \
    JVM_LOG_HOME="/logs/${APP_NAME}" \
    JAVA_TIMEZONE="Asia/Shanghai"

ENV SENTINEL_OPTS="-Dserver.port=8848 \
        -Dproject.name=${APP_NAME} \
        -Dcsp.sentinel.dashboard.server=${SENTINEL_DASHBOARD_SERVER} \
        -Dcsp.sentinel.log.dir=${SENTINEL_LOG_DIR} \
        -Dcsp.sentinel.metric.file.single.size=${SENTINEL_METRIC_FILE_SINGLE_SIZE} \
        -Dcsp.sentinel.metric.file.total.count=${SENTINEL_METRIC_FILE_TOTAL_COUNT}" \
    JAVA_OPTS="-Djava.security.egd=file:/dev/./urandom \
        -Duser.timezone=$JAVA_TIMEZONE \
        -Djava.awt.headless=true \
        -Djava.net.preferIPv4Stack=true \
        -Xloggc:/logs/gc.log \
        -XX:GCLogFileSize=10M \
        -XX:NumberOfGCLogFiles=10 \
        -XX:+UseGCLogFileRotation \
        -XX:+PrintGCDateStamps \
        -XX:+PrintGCTimeStamps \
        -XX:+PrintGCDetails \
        -XX:+PrintGCApplicationStoppedTime \
        -XX:+DisableExplicitGC \
        -XX:+HeapDumpOnOutOfMemoryError \
        -XX:HeapDumpPath=/logs/heapdump.hprof "

VOLUME /logs

COPY sentinel-dashboard-1.4.0.jar ${APP_NAME}.jar

EXPOSE 8848

ENTRYPOINT exec java -server -Xms512m -Xmx512m -Xmn256m -Xss256k ${SENTINEL_OPTS}  $JAVA_OPTS -jar /${APP_NAME}.jar \
    --spring.profiles.active=dev
