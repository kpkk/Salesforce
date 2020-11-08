pipeline {
  agent any
  stages {
    stage('Development') {
      steps {
        echo 'This will build the code and generate an artifact'
      }
    }

    stage('QA') {
      steps {
        git(url: 'https://github.com/kpkk/Salesforce.git', branch: 'master')
      }
    }

    stage('Deployment') {
      steps {
        input 'This needs manual intervention'
      }
    }

  }
}