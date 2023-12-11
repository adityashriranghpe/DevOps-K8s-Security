pipeline {
  agent any
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('SonarQube Analyses') {
     steps {
          withSonarQubeEnv('sonar6') {
            sh 'mvn sonar:sonar -Dsonar.host.url=http://192.168.0.229:9000 -Dsonar.login=admin -Dsonar.password=Adi@9922'
          }
     }
    }
  }
}
