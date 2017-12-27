Here you find a complex example. 

1. The property file uses inheritance
1. The property file does not use the default placeholder
1. The property value for log.level is overwritten by commandline
1. The database/datasource.config doesn't use the default placeholder
1. The pacify parameters are placed in a file
1. We use Archive in Archive replacement (deploymentPackage/server)
1. We use RegEx for referenced files (deploymentPackage/server)

<b></b>

    java -jar ../../pacify-shaded-*.jar    \  
         replace                           \
         @pacify.params
   
After that call, you find the dev1 configured package under deploymentPackage_dev1
  
   
