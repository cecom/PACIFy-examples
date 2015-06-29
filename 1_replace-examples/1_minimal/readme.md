Here you find a really simple example. Under "properties" you find the definition of the placeholders, this properties are normally provided by the ops team. Under "package" you find a deployment package, which is provided by the dev team, where some configuration is "needed". 

    java -jar ../../pacify-shaded-*.jar                  \  
         replace                                         \
	 --packagePath=deploymentPackage                 \
	 --copyTo=deploymentPackage_dev1                 \
	 --resolvers=FileResolver                        \
	 -RFileResolver.file=properties/dev1.properties
   
After that call, you find the dev1 configured package under deploymentPackage_dev1.
  
   
