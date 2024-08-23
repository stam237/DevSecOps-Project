pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo "building"
        sleep 3
      }
    }
    stage('Test Security') {
      steps {
        echo "testing"
        timeout(time: 15, unit: "MINUTES") {
	          input message: 'Do you want to review the security findings', ok: 'Yes'
	      }
        sleep 5
      }
    }
    stage('Deploy') {
      steps {
        echo "Deploy in production"
        sleep 10
      }
    }
  }
}
