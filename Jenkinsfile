pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
      }
    }
    stage('Parallel Tests') {
      failFast true
      parallel {
        stage('pytest unit tests') {
          steps {
            echo "On Branch A"
          }
        }
        stage('webdriver E2E tests') {
          steps {
            echo "On Branch B"
          }
        }
      }
    }
    stage("update docker/helm repos") {
      parallel {
        stage("docker") {
          stages {
            stage("docker build") {
              steps {
                echo "blah"
              }
            }
            stage("docker push") {
              steps {
                echo "blah"
              }
            }
          }
        }
        stage("helm") {
          stages {
            stage("helm package") {
              steps {
                echo "blah"
              }
            }
            stage("helm serve") {
              steps {
                echo "blah"
              }
            }
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying..'
      }
    }
    stage('Validate') {
      steps {
        echo 'Validate..'
      }
    }
  }
}





