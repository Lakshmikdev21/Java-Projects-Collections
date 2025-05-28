pipeline {

agent any

stages {
    stage('Clone') {
        steps {
            git branch: 'main', url: 'https://github.com/Lakshmikdev21/spring-petclinic.git'
        }
    }
    stage('Build') {
        steps {
            bat 'mvn package'
        }
    }
    
    stage('Test') {
        steps {
            bat 'mvn test'
        }
    }
    stage('Test Results Reports') {
        steps {
            junit 'target/surefire-reports/*.xml'
        }
    }
    
    stage('Artifacts') {
        steps {
            archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
        }
    }
    stage('Deploy') {
        steps {
            echo 'Hello World'
        }
    }
}
}