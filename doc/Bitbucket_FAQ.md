# Bitbucket FAQ

### Mingming configured the agent according to the document, and successfully activated the confluence, but when Bitbucket was activated, the generated key was prompted to be invalid.
This situation is often a problem with the `JAVA_OPTS` setting. If it is set according to the following method `JAVA_OPTS`, there will be activation failure
   * You can put: `export JAVA_OPTS="-javaagent:/path/to/atlassian-agent.jar ${JAVA_OPTS}"` into `.bashrc` or `. bash_profile` such a file.

The reason is that Bitbucket does not use this variable set globally, and mainly relies on the configuration in the `installation directory/bin/_start-webapp.sh` in its own directory, so edit this file and modify 

`JAVA_OPTS="-classpath $INST_DIR/app $JAVA_OPTS $BITBUCKET_ARGS $JMX_OPTS $JVM_REQUIRED_ARGS $JVM_SUPPORT_RECOMMENDED_ARGS"` 

where 

`JAVA_OPTS="-javaagent:/atlassian-agent storage directory/atlassian-agent.jar -classpath/atlassian-agent.jar -classpath/atlassian-agent.jar -classpathTS $ $ $BMXAR JVM_REQUIRED_ARGS $JVM_SUPPORT_RECOMMENDED_ARGS"`

Try to activate again



