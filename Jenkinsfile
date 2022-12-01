pipeline {
  agent any
  stages {
    stage('Fetch code') {
      steps {
        git(url: 'https://github.com/Vijaysapte/Blue-Ocean.git', branch: 'main', poll: true)
      }
    }

    stage('Install Apache') {
      steps {
        sh '''sudo yum install httpd -y
'''
      }
    }

    stage('Start HTTPD ') {
      steps {
        sh 'sudo service httpd start'
      }
    }

    stage('Deploy Application') {
      steps {
        sh 'sudo cp -R * /var/www/html'
      }
    }

  }
}