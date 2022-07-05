pipeline{
 agent any
 tools {
  jdk 'myjava'
  maven 'mymaven'
}
  stages{
    stage('checkout'){
      steps{
       checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/kliakos/sparkjava-war-example.git']]])
      }
    }
      stage('mvn'){
      steps{
       sh 'mvn package'
      }
    }
    stage('copy'){
      steps{
       echo 'copy'
      }
    }
  }
}
  
