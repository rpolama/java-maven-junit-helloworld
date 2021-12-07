pipeline {
  agent any
  tools {
    maven 'my_maven_3.8.1'
  }
  stages {
    stage("build") {
      steps {
        sh 'mvn clean install -DskipTests'
        echo 'Building..Pipeline'
      }
    }

    stage('unit-tests') {
      steps {
        echo "Unit Test"
        sh "mvn test"
      }
      post {
        always {
          junit '**/target/surefire-reports/*.xml'
        }
      }
    }

    stage("deploy") {
      steps {
        snDevOpsChange()
      }
    }
  }
}
