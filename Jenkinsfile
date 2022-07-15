pipeline {
  agent any
  tools {
    maven 'Maven' 
       }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Deploy To Tomcat Server') {
      steps{
        script {
        deploy adapters: [tomcat9(credentialsId: 'Deployer', path: '', url: 'http://3.84.2.133:8080/')], contextPath: '/web', war: '\'/hello-world/target/*.war\' '
      }
     }
   }
 }
}

