When PACIFy has to configure your package it has to resolve the placeholders. To resolve the placeholders PACIFy is asking the *Resolver*. PACIFy ships the CmdResolver as core module and here you find some examples on how you can use it. The CmdResolver is not really used to resolve all the Properties. It is mostly used to overwrite property values from other resolvers. See the MultiResolver Examples.

1. Here we resolve the properties via commandline and the result is written to stdout:  

        java -jar ../../pacify-shaded-*.jar       \
             createPropertyFile                   \
             --resolvers=CmdResolver              \
             -RCmdResolver.jdbc.host=example.org  \
             -RCmdResolver.jdbc.port=1521         \
             -RCmdResolver.jdbc.sid=xe            \
             -RCmdResolver.jdbc.url=jdbc:oracle:thin:@%{jdbc.host}:%{jdbc.port}/%{jdbc.sid} 

2. Same as first example, but result is written to result.txt:  
        
        java -jar ../../pacify-shaded-*.jar       \
             createPropertyFile                   \
             --destinationFile=result.txt         \
             --resolvers=CmdResolver              \
             -RCmdResolver.jdbc.host=example.org  \
             -RCmdResolver.jdbc.port=1521         \
             -RCmdResolver.jdbc.sid=xe            \
             -RCmdResolver.jdbc.url=jdbc:oracle:thin:@%{jdbc.host}:%{jdbc.port}/%{jdbc.sid}

3. Here we resolve the properties via commandline, using not the default tokens and the result is written to stdout: 		   

        java -jar ../../pacify-shaded-*.jar       \
             createPropertyFile                   \
             --resolvers=CmdResolver              \
             -RCmdResolver.beginToken=@{          \
             -RCmdResolver.endToken=}             \
             -RCmdResolver.jdbc.host=example.org  \  
             -RCmdResolver.jdbc.port=1521         \
             -RCmdResolver.jdbc.sid=xe            \
             -RCmdResolver.jdbc.url=jdbc:oracle:thin:@@{jdbc.host}:@{jdbc.port}/@{jdbc.sid}  
   
   
