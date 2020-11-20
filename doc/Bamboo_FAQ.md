# Bamboo FAQ

### Mingming configured the agent as stated in the document, and successfully activated confluence, but the generated key is invalid when Bamboo is activated.
This situation is often a problem with the setting of `JAVA_OPTS`, if it is set according to the following method `JAVA_OPTS`, there will be activation failure
   * You can put: `export JAVA_OPTS="-javaagent:/path/to/atlassian-agent.jar ${JAVA_OPTS}"` into `.bashrc` or `. bash_profile` such a file.

The reason is that Bamboo does not use this variable set globally, and it mainly relies on the configuration in `/bin/setenv.sh` under the installation directory in its own directory, so edit this file and modify 

`JAVA_OPTS="-Xms${ JVM_MINIMUM_MEMORY} -Xmx${JVM_MAXIMUM_MEMORY} ${JAVA_OPTS} ${JVM_REQUIRED_ARGS} ${JVM_SUPPORT_RECOMMENDED_ARGS} ${BAMBOO_HOME_MINUSD}"` 

is 

stored in the `JAVA_OPTS="-javasagent:/atlass. {JVM_MINIMUM_MEMORY} -Xmx${JVM_MAXIMUM_MEMORY} ${JAVA_OPTS} ${JVM_REQUIRED_ARGS} ${JVM_SUPPORT_RECOMMENDED_ARGS} ${BAMBOO_HOME_MINUSD}"`

Try to activate again


