node {
  def mvnHome
  def pom
  def artifactVersion
  def tagVersion
  def retrieveArtifact

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
