#!groovy

pipeline {
    agent any

    stages {
         stage('Preparation') { 
            steps {
                echo 'nothing to do'
            }
        }//nd stage prep
       
        stage('Build') { 
            steps {
                withEnv(["PATH+MAVEN=${tool 'M3'}/bin"]) {
                // sh "mvn --batch-mode -V -U -e clean deploy -Dsurefire.useFile=false"
                sh 'mvn -B -DskipTests clean package' 
                }
            }                
        }//nd stage build

        stage('Unit Test') { 
            steps {
               withEnv(["PATH+MAVEN=${tool 'M3'}/bin"]) {
                // sh "mvn --batch-mode -V -U -e clean deploy -Dsurefire.useFile=false"
                sh 'mvn test' 
               }
            }
            post {
                always{
                    junit 'target/surefire-reports/*.xml'
                }
            } 
        }//end unit test

    }//end stages
}