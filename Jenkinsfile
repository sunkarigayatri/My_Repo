pipeline {
  agent {
    docker { image 'maven:3.8.6-openjdk-11' }
  }
  stages {
    stage('Checkout Code') {
      steps {
        git branch: 'feature-jenkinsfile', url: 'https://github.com/sunkarigayatri/My_Repo.git'
      }
    }
    stage('Build JAR') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage('Archive Artifact') {
      steps {
        archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
      }
    }
  }
}

