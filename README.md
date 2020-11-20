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
Supports almost all Atlassian products, and supports plug-ins.
Support DataCenter mode.
Compared with the traditional crack, you can easily upgrade your service without having to crack it again.
Provide java-based command line keygen, which is more convenient to use in the terminal environment.
Open source projects, you know what you did when you cracked it.
Download
Download the release package of this project directly.
Compile by yourself
Clone the source code of this project, and the pom.xml mvn packagecan be compiled after execution in the same level directory .
If you don’t know what I’m talking about, it’s best to download the package I compiled directly.
Using help
If you have already obtained it atlassian-agent.jar, you can try to execute and java -jar atlassian-agent.jarsee the output help.
The help here uses Atlassian's Confluence service as an example.
Configure Agent
Put it atlassian-agent.jarin a location that you will not delete randomly (all Atlassian services on your server can share the same one atlassian-agent.jar).
Set the environment variable CATALINA_OPTS(this is actually the environment variable of Tomcat, which is used to specify the -javaagentparameters attached when starting the java program), and attach the parameters. Specifically, you can do this:
You can put: export CATALINA_OPTS="-javaagent:/path/to/atlassian-agent.jar ${CATALINA_OPTS}"such commands in .bashrcor .bash_profilesuch files.
You can put: export CATALINA_OPTS="-javaagent:/path/to/atlassian-agent.jar ${CATALINA_OPTS}"such a command in bin目录the setenv.shor under the service installation setenv.bat（供windows使用）.
You can also directly execute the command line: CATALINA_OPTS="-javaagent:/path/to/atlassian-agent.jar" /path/to/start-confluence.shto start your service.
Or you know other ways to modify environment variables, but if you have irrelevant Tomcat services on your machine, it is not recommended to modify global CATALINA_OPTSenvironment variables.
If you want to verify whether the configuration is successful, you can do this:
Execute similar commands: ps aux|grep javafind the corresponding process to see if the -javaagentparameters are correctly attached.
The software installation directory is similar /path/to/confluence/logs/catalina.out: ========= agent working =========the output of : should be found in the Tomcat log .
Use KeyGen
You have to confirm that the agent has been configured, refer to the above instructions.
When you try to execute java -jar /path/to/atlassian-agent.jarit, you should be able to see the output of KeyGen parameter help.
Please take a closer look at the function of each parameter, especially -pthe value range of the parameter.
When Atlassian service is installed, you should see AAAA-BBBB-CCCC-DDDDa server id similar to:, please pay attention.
Running KeyGen with correct parameters will output the calculated activation code on the terminal.
Copy the generated activation code to activate the service you want to use.
Affirm
This project is only for personal study and research purposes, not for commercial purposes!
For commercial use, please purchase genuine products from Atlassian , thank you for your cooperation!
This project uses an GNU General Public License v3.0open source license!
It is not allowed to say that my code is poorly written. For me, it PHPis the best language in the world (to argue against it).
