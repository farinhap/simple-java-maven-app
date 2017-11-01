pipeline {
    agent any
    def mvnHome
    stages {
         stage('Preparation') { 
        // Get the Maven tool.
         // ** NOTE: This 'M3' Maven tool must be configured
         // **       in the global configuration.           
         mvnHome = tool 'M3'
        }
       
        stage('Build') { 
            steps {
                sh '${mvnHome}/bin/mvn -B -DskipTests clean package' 
            }
        }
    }
}