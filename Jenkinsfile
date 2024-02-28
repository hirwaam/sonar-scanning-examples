node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'Maven 3.9.0';
    withSonarQubeEnv() {
      bat "cd ./sonarqube-scanner-maven/maven-basic/"
      bat "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=first-sq-analysis -Dsonar.projectName='first-sq-analysis'"
    }
  }
}
