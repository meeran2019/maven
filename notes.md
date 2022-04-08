---------------------------------------------------------------------------------------------------------
INTRODUCTION:
---------------------------------------------------------------------------------------------------------

    It is build tool.
    It helps to setup java application.
    Build tools automate the building process.
    It helps to download dependancy and corresponding versions during build. 

MAVEN CENTRAL REPOSITORY: 

    Any dependancy library can be get from repository.
    https://mvnrepository.com/repos/central

COMMANDS: 

    mvn --version               To check version.
    mvn archetype:generate      To download plugin for maven.
    mvn eclipse:eclipse         To convert project for eclipse 

MAVEN BUILD CYCLE: 

    mvn validate        validate project is correct and all information is available.
    mvn compile         compile the source code
    mvn test            execute the unit test in test directory.
    mvn package         jar/war file will be created.
    mvn install         install package code into local maven repository.
    mvn deploy          deploy to remote repository

    mvn clean           clean project working directory.

    Note: when run package, previous steps are executed. same for test and compile. 

POM.XML FILE: 

    Project Object Model
    It contains configuration details.
    All dependancies and support plugins defined.
    





