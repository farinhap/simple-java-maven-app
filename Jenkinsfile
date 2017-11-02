pipeline {
  agent any
  stages {
    stage('Preparation') {
      steps {
        echo 'nothing to do'
      }
    }
    stage('Build') {
      steps {
        withEnv(overrides: ["PATH+MAVEN=${tool 'M3'}/bin"]) {
          sh 'mvn -B -DskipTests clean package'
        }
        
      }
    }
    stage('Unit Test') {
      parallel {
        stage('Unit Test') {
          steps {
            withEnv(overrides: ["PATH+MAVEN=${tool 'M3'}/bin"]) {
              sh 'mvn test'
            }
            
          }
          post {
            always {
              junit 'target/surefire-reports/*.xml'
              
            }
            
          }
        }
        stage('Code Analysis') {
          steps {
            tool 'kiuwan'
          }
        }
      }
    }
  }
}