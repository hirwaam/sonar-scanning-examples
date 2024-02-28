node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'Default Maven';
    withSonarQubeEnv() {
      sh "cd ./sonarqube-scanner-maven/maven-basic/"
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=first-sq-analysis -Dsonar.projectName='first-sq-analysis'"
    }
  }
}
