Atlassian Agent
Support (almost any version):
JIRA Software
JIRA Core
JIRA Service Desk
JIRA plugin: Capture
JIRA plugin: Training
JIRA plugin: Portfolio
Confluence
Confluence plugin: Questions
Confluence plugin: Team Calendars
Bamboo
Bitbucket
FishEye
Crowd
Crucible

Instructions for use
Advantage
It supports almost all products of Atlassian family and supports plug-ins.
Support DataCenter mode.
Compared with the traditional crack, you can easily upgrade your service without having to crack it again.
Provide java-based command line keygen, which is more convenient to use in the terminal environment.
Open source projects, you know what you did when you cracked it.
Download
Download the release package of this project directly.
Compile by yourself
Clone the source code of this project, and the pom.xml directory can be compiled after executing mvn package.
If you don’t know what I’m talking about, it’s best to download the package I compiled directly.
Using help
If you have already obtained atlassian-agent.jar, you can try to execute java -jar atlassian-agent.jar to see the help output.
The help here uses Atlassian's Confluence service as an example.
Configure Agent
Put atlassian-agent.jar in a location that you will not delete randomly (all Atlassian services on your server can share the same atlassian-agent.jar).
Set the environment variable CATALINA_OPTS (this is actually the environment variable of Tomcat, which is used to specify the parameters attached when starting the java program), and attach the -javaagent parameter. Specifically, you can do this:
You can put commands like export CATALINA_OPTS="-javaagent:/path/to/atlassian-agent.jar ${CATALINA_OPTS}" into a file like .bashrc or .bash_profile.
You can put commands like export CATALINA_OPTS="-javaagent:/path/to/atlassian-agent.jar ${CATALINA_OPTS}" into setenv.sh or setenv.bat in the bin directory where the service is installed (for windows use) in.
You can also directly execute the command line: CATALINA_OPTS="-javaagent:/path/to/atlassian-agent.jar" /path/to/start-confluence.sh to start your service.
Or you know other ways to modify environment variables, but if you have irrelevant Tomcat services on your machine, it is not recommended to modify the global CATALINA_OPTS environment variable.
If you want to verify whether the configuration is successful, you can do this:
Execute a similar command: ps aux|grep java Find the corresponding process to see if the -javaagent parameter is correctly attached.
Similar to the software installation directory: /path/to/confluence/logs/catalina.outTomcat log should be able to find: ========= agent working ========= output words.
Use KeyGen
You have to confirm that the agent has been configured, refer to the above instructions.
When you try to execute java -jar /path/to/atlassian-agent.jar, you should be able to see the output KeyGen parameter help.
Please take a closer look at the role of each parameter, especially the value range of the -p parameter.
You should see a server id similar to: AAAA-BBBB-CCCC-DDDD during Atlassian service installation. Please pay attention.
Running KeyGen with correct parameters will output the calculated activation code on the terminal.
Copy the generated activation code to activate the service you want to use.
Affirm
This project is only for personal study and research purposes, not for commercial purposes!
For commercial use, please purchase genuine copies from Atlassian, thank you for your cooperation!
This project uses GNU General Public License v3.0 open source license!
It is not allowed to say that my code is poorly written. For me, PHP is the best language in the world.
communicate with
Issue an issue to this project.
You are welcome to improve this project together, please send a PR.
You can join the QQ group: 30347511 and chat with me in real time.
Visit the website: https://zhile.io and leave me a message.
