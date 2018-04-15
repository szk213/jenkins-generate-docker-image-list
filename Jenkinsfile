pipeline {
  agent any
  stages {
    stage('DR image list') {
      steps {
        script {
          httpRequest "http://192.168.0.150/api/repositories/abc%2Ftest/tags"
        }

      }
    }
  }
}