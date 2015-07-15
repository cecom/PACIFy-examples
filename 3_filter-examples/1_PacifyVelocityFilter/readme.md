PACIFy's default filter is com.geewhiz.pacify.filter.PacifyTokenFilter. This filter can only handle simple **placeholders**. The com.geewhiz.pacify.filter.PacifyVelocityFilter can handle velocity templates. This example is a simple demonstration.

1. The configuration config/app.properties uses if/else statements
1. The configuration config/app.properties uses foreach statements
1. The foreach splits a property into a list and creates an config section per entry

<b></b>

    java -jar ../../pacify-shaded-*.jar    \  
         replace                           \
         --packagePath=deploymentPackage   \          
         --copyTo=deploymentPackage_dev1   \
         --resolvers=FileResolver          \
         -RFileResolver.file=properties/dev1.properties
         
   
After that call, you find the dev1 configured package under deploymentPackage_dev1
  
   
