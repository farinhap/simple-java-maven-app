pipeline {
    agent any

    tools{
        maven 'M3' 
    }

    stages {
         stage('Preparation') { 
        // Get the Maven tool.
         // ** NOTE: This 'M3' Maven tool must be configured
         // **       in the global configuration.           
        steps{
            echo 'nothing to do'
        }
        }
       
        stage('Build') { 
            steps {
                sh '${mvnHome}/bin/mvn -B -DskipTests clean package' 
            }
        }
    }
}