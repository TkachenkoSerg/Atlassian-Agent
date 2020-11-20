# Confluence FAQ

### Windows activation at Confluence Precautions

* Do not use the start-service.bat start (if you have to start so he went to the registry change -javaagent parameters)
* Use bin \ start-confluence.bat start
at * Add the -javaagent parameter to bin\setenv.bat
* There is a bug in Confluence under Windows, you need to modify setenv.bat to fix

 ```bash
set CATALINA_OPTS=-Xloggc:"%atlassian_logsdir%\gc-%atlassian_timestamp%.log" %CATALINA_OPTS%
//to
Changeset CATALINA_OPTS=-Xloggc:"%atlassian_logsdir%\gc-%%t.log" %CATALINA_OPTS%
```



