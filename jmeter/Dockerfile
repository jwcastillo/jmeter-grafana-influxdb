FROM openjdk:17-alpine


ARG jmeterVersion
ARG JMETER_HOME="/jmeter"
ARG JMETER_PLUGINS_PATH="${JMETER_HOME}/lib/ext"
ENV JMETER_VERSION ${jmeterVersion}
RUN wget -O /apache-jmeter.tgz http://mirror.its.dal.ca/apache/jmeter/binaries/apache-jmeter-${JMETER_VERSION}.tgz \
  && tar -xvzf apache-jmeter.tgz \
  && rm apache-jmeter.tgz \
  && mv apache-jmeter-${JMETER_VERSION} ${JMETER_HOME}
ENV JMETER_PMANAGER_VERSION 1.7
ENV CMDRUNNER_VERSION 2.2
RUN wget -O ${JMETER_PLUGINS_PATH}/jmeter-plugins-manager-${JMETER_PMANAGER_VERSION}.jar https://repo1.maven.org/maven2/kg/apc/jmeter-plugins-manager/${JMETER_PMANAGER_VERSION}/jmeter-plugins-manager-${JMETER_PMANAGER_VERSION}.jar  \
  && wget -O ${JMETER_HOME}/lib/cmdrunner-${CMDRUNNER_VERSION}.jar  https://repo1.maven.org/maven2/kg/apc/cmdrunner/${CMDRUNNER_VERSION}/cmdrunner-${CMDRUNNER_VERSION}.jar \ 
  && java -cp ${JMETER_PLUGINS_PATH}/jmeter-plugins-manager-${JMETER_PMANAGER_VERSION}.jar org.jmeterplugins.repository.PluginManagerCMDInstaller \
  && ${JMETER_HOME}/bin/PluginsManagerCMD.sh install-all-except \
  && ${JMETER_HOME}/bin/PluginsManagerCMD.sh status \
  && chmod +x ${JMETER_HOME}/bin/*.sh

WORKDIR /jmeter
COPY . /jmeter

ENV JMETER_HOME ${JMETER_HOME}
ENV PATH ${JMETER_HOME}/bin:$PATH
ENV testDir /jmeter/test
RUN sed -i "s|user.properties=user.properties|user.properties=${testDir}/user.properties|g; \
	    s|#javascript.use_rhino=false|javascript.use_rhino=true|g" ${JMETER_HOME}/bin/jmeter.properties

RUN chmod +x ./entrypoint.sh


COPY entrypoint.sh /entrypoint.sh

CMD /bin/sh ./entrypoint.sh