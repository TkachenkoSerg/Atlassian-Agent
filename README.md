# Atlassian Agent

#### Support (almost any version):
* JIRA Software
* JIRA Core
* JIRA Service Desk
* JIRA plugin: Capture
* JIRA plugin: Training
* JIRA plugin: Portfolio
* Confluence
* Confluence plugin: Questions
* Confluence plugin: Team Calendars
* Bamboo
* Bitbucket
* FishEye
* Crowd
* Crucible

## Instructions for use

### Advantages
* Support almost all Atlassian products, and support plug-ins.
* Support DataCenter mode.
* Compared with the traditional crack, you can easily upgrade your service without having to crack it again.
* Provide java-based command line keygen, which is more convenient to use in the terminal environment.
* Open source project, you know what you did when you cracked it.

### Direct download
* Directly download the release package of this project.

### Compile by
yourself* Clone the source code of this project, and you can compile after executing `mvn package` in the pom.xml same level directory.
* *If you don’t know what I’m talking about, it’s best to download my compiled package directly. *

### Use help
* If you have already obtained `atlassian-agent.jar`, you can try to execute `java -jar atlassian-agent.jar` to see the output help.
* The help here uses Atlassian's Confluence service as an example.

### Configure Agent
1. Put `atlassian-agent.jar` in a location that you will not delete randomly (all Atlassian services on your server can share the same `atlassian-agent.jar`).
2. Set the environment variable `CATALINA_OPTS` (this is actually the environment variable of Tomcat, which is used to specify the parameters attached when starting the java program), and attach the `-javaagent` parameter. Specifically, you can do this:
   * You can put commands like `export CATALINA_OPTS="-javaagent:/path/to/atlassian-agent.jar ${CATALINA_OPTS}"` into `.bashrc` or `.bash_profile` File.
   * You can put commands like `export CATALINA_OPTS="-javaagent:/path/to/atlassian-agent.jar ${CATALINA_OPTS}"` to `setenv.sh` or `under the `bin directory` where the service is installed setenv.bat (for windows use)`.
   * You can also directly execute the command line: `CATALINA_OPTS="-javaagent:/path/to/atlassian-agent.jar" /path/to/start-confluence.sh` to start your service.
   * Or you know other ways to modify environment variables, but if you have irrelevant Tomcat services on your machine, it is not recommended to modify the global `CATALINA_OPTS` environment variable.
3. If you want to verify whether the configuration is successful, you can do this:
   * Execute a similar command: `ps aux|grep java` to find the corresponding process and see if the `-javaagent` parameter is correctly attached.
   * Similar to the software installation directory: `/path/to/confluence/logs/catalina.out` Tomcat log should be found: `========= agent working =========` The output words.

### Use KeyGen
* You have to confirm that the agent has been configured, refer to the above instructions.
* When you try to execute `java -jar /path/to/atlassian-agent.jar`, you should be able to see the output of KeyGen parameter help.
* Please take a closer look at the function of each parameter, especially the value range of the `-p` parameter.
* During the Atlassian service installation, you should see a server id similar to: `AAAA-BBBB-CCCC-DDDD`, please pay attention.
* After providing the correct parameters, running KeyGen will output the calculated activation code on the terminal.
* Copy the generated activation code to activate the service you want to use.

### Affirmation
* This project is only for personal study and research purposes, not for commercial purposes!
* For commercial use, please purchase genuine from [Atlassian](https://www.atlassian.com), thank you for your cooperation!
* This project uses `GNU General Public License v3.0` open source license!
* It is not allowed to say that my code is badly written. For me, `PHP` is the best language in the world (to argue with dissatisfaction).
