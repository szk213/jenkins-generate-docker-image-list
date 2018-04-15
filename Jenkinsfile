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
          taglist = props.collectMany{ it["name"] }
          writeYaml file: 'taglist.yaml', data: taglist
        }

        sh "echo '${response.content}'"
      }
    }
  }
}