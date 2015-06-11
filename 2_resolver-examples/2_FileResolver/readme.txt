When PACIFy has to configure your package it has to resolve the placeholders. To resolve the placeholders PACIFy is asking the *Resolver*. PACIFy ships the FileResolver as core module and here you find some examples on how you can store your property values. The FileResolver reduces the administration of your properties to a minimum! 

1. A simple example. Resolving the 1_minimal/minimal.properties:

   java -jar ../../pacify-shaded-*.jar  \
           createPropertyFile           \
		   --resolvers=FileResolver     \
		   -RFileResolver.file=1_minimal/minimal.properties

2. The property file 2_customToken/customToken.properties doesn't use the default tokens for property references:

   java -jar ../../pacify-shaded-*.jar   \
           createPropertyFile            \
		   --resolvers=FileResolver      \
		   -RFileResolver.beginToken=@{  \
		   -RFileResolver.endToken=}     \
		   -RFileResolver.file=2_customToken/customToken.properties 

3.  Under 3_inheritance you find an inheritance example. Dev1 and Dev2 are using the default "dev" settings. But dev1 uses "mock" and dev2 uses "real" endpoints for their service calls. 

   java -jar ../../pacify-shaded-*.jar  \
          createPropertyFile            \
		  --resolvers=FileResolver      \
		  -RFileResolver.file=3_inheritance/dev/dev1.properties
		  
    java -jar ../../pacify-shaded-*.jar \ 
          createPropertyFile            \
		  --resolvers=FileResolver      \
		  -RFileResolver.file=3_inheritance/dev/dev2.properties
