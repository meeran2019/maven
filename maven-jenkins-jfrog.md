CREATE THE MAVEN PROJECT: 

    1. Create the maven project directory, 
            mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false

    2. Upload the code to git repository.
    3. Create the jenkins: 
            1. Install plugin "artifactory"
            2. Source - github project.
            3. Build Environment -> Maven3-Artifactory Integration.
                    Select Target release & snapshot repository.
            4. Build Environment -> Deploy to Artifacts. 
            5. In Build -> Invoke Artifactory Maven 3
                    Mvn golas -> clean install  -Dartifactory.publish.artifacts=true -Dartifactory.publish.buildInfo=true  or clean install

                
            