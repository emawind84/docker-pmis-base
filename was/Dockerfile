FROM dev.sangah.com:5043/tomcat-base

COPY server.xml.template /usr/local/tomcat/conf/
ONBUILD COPY stnd_pmis.war /usr/local/src/

# force locale to Korean
ENV LC_ALL=ko_KR.UTF8

EXPOSE 8080
EXPOSE 8081

# don't add anything else after this!
COPY docker-entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
#CMD ["catalina.sh", "run"]

HEALTHCHECK CMD curl --fail http://localhost:8080/ || exit 1
