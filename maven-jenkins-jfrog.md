
CREATE THE MAVEN PROJECT: 

    1. Create the maven project directory, 
            mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false

CREATE THE JFROG: 

    1. Signup for the jfrog cloud https://my.jfrog.com/login and create the artifactory.
    2. Welcome -> New Local Repository (select package type, package name)
    3. Under Artifactory -> Artifacts -> Created repository will be listed.

CREATE THE JENKINS: 

    1. Manage Jenkins -> Configure System -> search jfrog and enter the artifactory and credential login.
    2. Create the job usig below, 
        1. Install plugin "artifactory"
        2. Source - github project.
        3. Build Environment -> Maven3-Artifactory Integration.
                Select Target release & snapshot repository.
        4. Build Environment -> Deploy to Artifacts. 
        5. In Build -> Invoke Artifactory Maven 3
                Mvn golas -> clean install  -Dartifactory.publish.artifacts=true -Dartifactory.publish.buildInfo=true  or clean install

                
            