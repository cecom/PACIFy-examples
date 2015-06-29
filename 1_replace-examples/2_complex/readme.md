Here you find a complex example. 

1. The property file uses inheritance
2. The property file does not use the default placeholder 
3. The property value for log.level is overwritten by commandline
4. The database/datasource.config doesn't use the default placeholder
5. The pacify parameters are placed in a file

    java -jar ..\..\pacify-shaded-*.jar    \  
         replace                           \
	 @pacify.params
   
After that call, you find the dev1 configured package under deploymentPackage_dev1
  
   
