node {
  stage('Clone the Git') {
    git 'https://github.com/tchowdary58/teja.git'
  }
  stage('SonarQube analysis') {
    def scannerHome = tool 'SonarQube';
    withSonarQubeEnv('SonarQube') {
      sh "${scannerHome}/bin/sonar-scanner \
      -D sonar.login=admin \
      -D sonar.password=Kasturi@08 \
      -D sonar.projectKey=project \
      -D sonar.exclusions=vendor/**,resources/**,**/*.java \
      -D sonar.host.url=http://localhost:9000/"
    }
  }
}
