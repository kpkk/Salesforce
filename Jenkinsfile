pipeline {
  agent any
  stages {
    stage('Development') {
      steps {
        echo 'This will build the code and generate an artifact'
      }
    }

    stage('QA') {
      parallel {
        stage('QA') {
          steps {
            git(url: 'https://github.com/kpkk/Salesforce.git', branch: 'master')
          }
        }

        stage('smoke test') {
          steps {
            git(branch: 'master', url: 'https://github.com/kpkk/Salesforce.git')
            bat 'mvn -f Salesforce/pom.xml test -Durl="https://login.salesforce.com"'
          }
        }

      }
    }

    stage('Deployment') {
      steps {
        input 'This needs manual intervention'
      }
    }

  }
}