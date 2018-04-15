pipeline {
  agent any
  stages {
    stage('DR image list') {
      steps {
        script {
          response = httpRequest "http://192.168.0.150/api/repositories/abc%2Ftest/tags"
          props = readJSON text: response.content
          props.each{
            println it.name
          }
        }

        sh "echo '${response.content}'"
      }
    }
  }
}