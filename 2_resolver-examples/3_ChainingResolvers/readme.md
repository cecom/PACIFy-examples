When PACIFy has to configure your package it has to resolve the placeholders. To resolve the placeholders PACIFy is asking the *Resolver*. PACIFy ships the FileResolver and the CmdResolver as core module, but you can write your own resolver, add it to the classpath and PACIFy can *see* it. 

Here you find some examples on how you can chain the resolvers and how you can than overwrite some properties. If PACIFy need to resolve a property and/or a token in a property, it will ask the resolvers in the given chain. If the first resolver does not have the property, PACIFy ask the next resolver and so on. Really powerful!


1. In this example, we overwrite the log.level with DEBUG via commandline:

        java -jar ../../pacify-shaded-*.jar        \
             createPropertyFile                    \
             --resolvers=CmdResolver,FileResolver  \
             -RCmdResolver.log.level=DEBUG         \
             -RFileResolver.file=inheritance/dev/dev1.properties
   
