pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
              withMaven (maven: 'maven-3.8.1') {
                sh "mvn clean install -Dmaven.test.skip=true"
              }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                //snDevOpsChange()
                echo 'Deploying....'
            }
        }
    }
}
