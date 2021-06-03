



New runtime versions of OABuilder are stored in the oabuilder-run github repo.

Each version will be stored under a new github tag.
    ex: 3.0.3

Set version (multiple places):
    src/main/java/com/viaoa/builder/resource/values.properties
    pom.xml
    package/windows/OABuilder.iss

update OABuilder-Help project with new version
    branch:dev
    pom.xml
    master branch merge dev, and then create a tag for the version

make sure that pom.xml has correct versions for dependencies
    oabuilder-help, etc

Update help
    see OABuilder-Help/doc/readme.txt
    




To build Windows installer 

    20200108 using new jpackage from JDK 14 EA
    *****************************
    ** see JPackage_ReadME.txt **  <<<<<<<<<<<<<<<<<<<
    *****************************
    
    
  qqqqqqqq NOT USED qqqqqqqqqqqq  ** this was before using jpackage, using jdk1.8 and ant script for javapackager
    1: create template.zip
        in project OATemplate
            run ANT (build.xml) target name="CreateTemplateZipFile"
                creates: dist/template.zip
         copy OATemplate/dist/template.zip to OABuilder/package 
    
    2: copy OABuilder-Models/model Demo.obx, OATemplate.obx, OABuilderModel.obx to OABuilder/package 
    
    3: copy OABuilder\runtime\OABuilder.obx to OABuilder/package
        might want to edit and remove most recent models
    
    4: run mvn (pom.xml) install to create target/oabuilder-3.0.3.jar  (uber jar)
        copy oabuilder-3.0.3.jar and rename to package/oabuilder.jar
             
    5: run ANT (build.xml) target name="JavaPackager"
        this will create package/bundles/*.exe

        delete package/*.jnlp and OABuilder.html
    
    6: copy package/bundles/*.exe to OABuilder-Run/windows-installer
        
    7: copy files only (no directories) from package/*.* to OABuilder-Run/executable-jar
        
    8: commit & push oabuilder-run to github

    
To run as executable jar file
    1: copy files (not directories) from oabuilder-run/executable-jar to a directory on users computer
    
    2: java -jar oabuilder.jar
    
Notes:
    if updating files manually, then remove the OATemplate directory.
    
    
        