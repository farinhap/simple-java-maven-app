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
                echo 'maven is ${maven} '
            }
        }
       
        stage('Build') { 
            steps {
                sh '${M2_HOME}/bin/mvn -B -DskipTests clean package' 
            }
        }
    }
}