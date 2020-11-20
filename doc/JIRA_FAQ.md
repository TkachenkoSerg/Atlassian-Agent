# JIRA FAQ

### Mingming configured the agent according to the document, and successfully activated the confluence, but when JIRA was activated, it prompted that the generated key was invalid.
This situation is often caused by the `JAVA_OPTS` setting. `JAVA_OPTS`, there will be activation failure
   * You can put: `export JAVA_OPTS="-javaagent:/path/to/atlassian-agent.jar ${JAVA_OPTS}"` into `.bashrc` or `. bash_profile` such a file.

The reason is that JIRA does not use this variable set globally, and it mainly relies on the configuration in the `/bin/setenv.sh` under the installation directory in its own directory, so edit this file and add `JAVA_OPTS="-javaagent: /atlassian-agent storage directory/atlassian-agent.jar $JAVA_OPTS"` at `JAVA_OPTS`, then try to activate again



