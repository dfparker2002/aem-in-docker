# Use the previously created aem-base-image
FROM aem-base-image

# Expose AEM author in port 4502
EXPOSE 4502 30303 22

# COPY SUPPORT FILES
ADD start /opt/aem/crx-quickstart/bin/
ADD quickstart /opt/aem/crx-quickstart/bin/

# SET EXEC
RUN chmod +x /opt/aem/crx-quickstart/bin/quickstart
RUN chmod +x /opt/aem/crx-quickstart/bin/start

# Make the container start always in Author mode with Port 4502
ENTRYPOINT ["java", "-jar", "cq-quickstart.jar", "-Dsling.run.modes=author", "-p", "4502"]
#, "-D", "'CQ_JVM_OPTS=-Xmx2048m -XX:MaxPermSize=512M -Xms32m -XX:+HeapDumpOnOutOfMemoryError -Doak.queryLimitInMemory=500000 -Doak.queryLimitReads=100000 -agentlib:jdwp=transport=dt_socket,address=30303,server=y,suspend=n'"
