pipeline {
    agent any

    tool{
        Maven 'apache-maven-3.3.9' 
    }

    stages {
         stage('Preparation') { 
        // Get the Maven tool.
         // ** NOTE: This 'M3' Maven tool must be configured
         // **       in the global configuration.           
        
        }
       
        stage('Build') { 
            steps {
                sh '${mvnHome}/bin/mvn -B -DskipTests clean package' 
            }
        }
    }
}