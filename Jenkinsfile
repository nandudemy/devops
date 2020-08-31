

properties([pipelineTriggers([githubPush()])])
node {
  def mvnHome
  def pom
  def tagVersion
 

  stage('Prepare') {
    mvnHome = tool 'maven'
  }

  stage('Checkout') {
     checkout scm
  }

  stage('Build') {
     if (isUnix()) {
        sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
     } else {
        bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
     }
  }
   
  
  }


