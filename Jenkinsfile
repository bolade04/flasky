pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/valeriedarling/flask', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t valeriedarling/flask_app .'
      }
    }

    stage('Docker Login') {
      steps {
        sh 'docker login -u valeriedarling -p dckr_pat_vDYznfUZxiZNyrpfqDBiz1yz12E'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push valeriedarling/flask_app'
      }
    }

  }
}