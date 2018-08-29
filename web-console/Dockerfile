FROM tomcat:9.0
WORKDIR /usr/local/tomcat/webapps/ROOT

ENV managerServicesUrl http://product_manager:8080

ENV consoleBackstageHost http://scene_init:8080

RUN rm -rf /usr/local/tomcat/webapps/ROOT/*

COPY web-console/target/web-console $WORKDIR
RUN sed -i "2i /usr/local/tomcat/webapps/ROOT/initDemo.sh" /usr/local/tomcat/bin/catalina.sh
RUN chmod 777 /usr/local/tomcat/webapps/ROOT/initDemo.sh
CMD ["catalina.sh", "run"]