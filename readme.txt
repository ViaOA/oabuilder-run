
** See: OABuilder doc/installer_readme.txt 

New runtime versions of OABuilder are stored in the oabuilder-run github repo.

Each version will be stored under a new github tag.
    ex: 3.2.1

Set version (multiple places):
    src/main/java/com/viaoa/builder/resource/values.properties
    pom.xml
    package/windows/OABuilder.iss (??)

update OABuilder-Help project with new version
    branch:dev
    pom.xml
    master branch merge dev, and then create a tag for the version

make sure that pom.xml has correct versions for dependencies
    oabuilder-help, etc

Update help
    see OABuilder-Help/doc/readme.txt
    


    
To run as executable jar file
    1: copy files (not directories) from oabuilder-run/executable-jar to a directory on users computer
    
    2: java -jar oabuilder.jar
    
Notes:
    if updating files manually, then remove the OATemplate directory.
    
    
        