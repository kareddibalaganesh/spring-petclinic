pipeline {

agent any

stages {
    stage('Clone') {
        steps {
            git branch: 'main', url: 'https://github.com/kareddibalaganesh/spring-petclinic.git'
        }
    }
    
      stage('Build') {
        steps {
           bat 'mvn clean install'
        }
    }
      stage('Test') {
        steps {
           bat 'mvn test'
        }
    }
    
      stage('Generate Junit Test Results') {
        steps {
           junit 'target/surefire-reports/*.xml'
        }
    }
    
      stage('Generate Artifacts') {
        steps {
           archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
        }
    }
}
}

