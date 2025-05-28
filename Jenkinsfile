pipeline {

agent any

stages {
    stage('Clone') {
        steps {
            git credentialsId: 'github', url: 'https://github.com/Lakshmikdev21/Java-Projects-Collections.git'
        }
    }
    stage('Build') {
        steps {
            bat 'mvn package'
        }
    }
    stage('Artifacts') {
        steps {
            archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
        }
    }
    stage('Deploy') {
        steps {
            deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'Tomcat', path: '', url: 'http://localhost:8080/')], contextPath: 'Glk Java Projects', war: 'target/*.war'
        }
    }
}
}
