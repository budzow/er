node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool '3.8.6';
    withSonarQubeEnv(credentialsId: 'SonarQube9Token', installationName: 'SonarQube9') {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=a"
    }
  }
}
