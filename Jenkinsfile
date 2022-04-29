pipeline {
  agent any
  stages {
    stage('validate') {
      parallel {
        stage('validate') {
          steps {
            echo 'Validate'
          }
        }

        stage('compile') {
          steps {
            sh 'echo "compile stage"'
          }
        }

        stage('test compile') {
          steps {
            sh 'sh \'echo "test compile job"\''
          }
        }

      }
    }

    stage('test') {
      parallel {
        stage('test') {
          steps {
            echo 'test the code'
          }
        }

        stage('code coverage') {
          steps {
            echo 'code coverage job'
          }
        }

      }
    }

    stage('Build') {
      agent any
      steps {
        echo 'Build job'
      }
    }

  }
  environment {
    CC = 'Any'
  }
}