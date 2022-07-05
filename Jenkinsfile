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
       sh 'cp /var/lib/jenkins/workspace/dsl-dev/target/sparkjava-hello-world-1.0.war /opt/softwares/apache-tomcat-9.0.64/webapps'
      }
    }
  }
}
  
