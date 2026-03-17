pipeline {
  agent any
  stages {
    stage('Verify Files') {
      steps {
        sh '''echo "Checking project files..."
ls -l
test -f index.html'''
      }
    }

    stage('Deploy') {
      steps {
        sh '''echo "Deploying calculator app..."
sudo mkdir -p ${DEPLOY_PATH}
sudo cp index.html ${DEPLOY_PATH}/index.html
sudo chmod -R 755 ${DEPLOY_PATH}'''
      }
    }

  }
  environment {
    DEPLOY_PATH = '/var/www/html/calculator-app'
  }
  post {
    success {
      echo 'Pipeline completed successfully.'
    }

    failure {
      echo 'Pipeline failed.'
    }

  }
}