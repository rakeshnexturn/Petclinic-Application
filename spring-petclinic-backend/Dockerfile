FROM openjdk:17

# Copy both JAR files to the container
COPY target/spring-petclinic-rest-2.2.5.jar /opt/spring-petclinic-rest-2.2.5.jar
COPY elastic-apm-agent-1.43.0.jar /

# Set the working directory
WORKDIR /opt

# Specify the entrypoint and command
ENTRYPOINT ["sh", "-c"]
CMD ["java", "-javaagent:/elastic-apm-agent-1.43.0.jar", "-Delastic.apm.service_name=demo", "-Delastic.apm.secret_token=Pe0wcjHdiSHTkw6wIn", "-Delastic.apm.server_url=https://5602858c918a4628985b301a945d7c6d.apm.eastus2.azure.elastic-cloud.com:443", "-Delastic.apm.environment=my-environment", "-Delastic.apm.application_packages=com.bezkoder", "-jar", "/opt/spring-petclinic-rest-2.2.5.jar"]
