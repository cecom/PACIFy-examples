Here an example, where you preconfigure some values. In this case, onle the error level is replaced and the configuration marker file is adjusted.

    java -jar ../../pacify-shaded-*.jar                  \
         preConfigure                                    \
         --packagePath=deploymentPackage                 \
         --copyTo=deploymentPackage_ALL                  \
         --resolvers=FileResolver                        \
         -RFileResolver.file=properties/preConf.properties
   
After that call, you find the dev1 configured package under deploymentPackage_ALL.
  
   
