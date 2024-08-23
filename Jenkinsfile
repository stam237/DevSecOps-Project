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

    stage('Approve based on environment lead') {
	          input {
	              message 'Please select environment'
	              id 'envId'
	              ok 'Submit'
	              submitterParameter 'approverId'
	              parameters {
	                  choice choices: ['Prod', 'Pre-Prod'], name: 'envType'
	              }
	          }

	            steps {
	                echo "Deployment approved to ${envType} by ${approverId}."

	            }
	    }

    stage('Deploy') {
      steps {
        echo "Deployement ongoing "
        sleep 10
      }
    }
  }
}

