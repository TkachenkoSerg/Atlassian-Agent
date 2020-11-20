# FishEye & Crucible FAQ

### Obviously configured the agent as stated in the document and successfully activated confluence, but when FishEye or Crucible is activated, it prompts that the generated key is invalid.
This situation is often caused by the `JAVA_OPTS` setting. According to the setting of `JAVA_OPTS` in the following way, activation failure will occur
   * You can put: `export JAVA_OPTS="-javaagent:/path/to/atlassian-agent.jar ${JAVA_OPTS}"` into `.bashrc `Or `.bash_profile`.

The reason is that FishEye and Crucible do not directly use this environment variable, instead of using the environment variable `FISHEYE_OPTS`,

so we open the fisheyectl.sh file in the bin directory and change the file

```FISHEYE_CMD="$JAVACMD $FISHEYE_OPTS -Dfisheye .library.path=$FISHEYE_LIBRARY_PATH -Dfisheye.inst=$FISHEYE_INST -Djava.awt.headless=true -Djava.endorsed.dirs=$FISHEYE_HOME/lib/endorsed -jar $FISHEYE_HOME/fisheyeboot.jar"```

Add to

` ``FISHEYE_CMD="$JAVACMD $FISHEYE_OPTS -javaagent:/path/to/atlassian-agent-v1.2.2/atlassian-agent.jar -Dfisheye.library.path=$FISHEYE_LIBRARY_PATH -Dfisheye.inst=$FISHEYE_INST -Djava.awt .headless=true -Djava.endorsed.dirs=$FISHEYE_HOME/lib/endorsed -jar $FISHEYE_HOME/fisheyeboot.jar"```

Retry activation again.



