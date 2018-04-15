pipeline {
  agent any
  stages {
    stage('DR image list') {
      steps {
        script {
          response = httpRequest "http://192.168.0.150/api/repositories/abc%2Ftest/tags"
          params.resContent = response.content
        }

        sh "echo '${response.content}'"
      }
    }
  }
}