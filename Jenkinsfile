node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvnHome = tool 'M3'
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=ta-user-service -Dsonar.projectName='ta-user-service'"
    }
  }
}