# Crowd FAQ

### Obviously configure the agent as stated in the document, and successfully activate the confluence, but when Crowd is activated, it prompts that the generated key is invalid.
This situation is often caused by the `JAVA_OPTS` setting. `JAVA_OPTS`, there will be activation failure
   * You can put: `export JAVA_OPTS="-javaagent:/path/to/atlassian-agent.jar ${JAVA_OPTS}"` into `.bashrc` or `. bash_profile` such a file.

The reason is that Crowd does not use the globally set variable, and it mainly relies on the configuration in the `installation directory /apache-tomcat/bin/setenv.sh` in its own directory, so edit this file and add `JAVA_OPTS= "-javaagent:/atlassian-agent storage directory/atlassian-agent.jar $JAVA_OPTS"`, try to activate again



