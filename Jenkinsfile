pipeline {
  agent {
    node {
      label 'workstation'
    }
  }

  parameters {
    choice(name: 'env', choices: ['dev', 'prod'], description: 'Pick environment')
    string(name: 'component', defaultValue: '', description: 'component name')
  }

  stages {
    stage('Ansible') {
      steps {
        sh 'ansible-playbook -i ${component}-${env}.gilbraltar.co.uk, roboshop.yml -e ansible_user=centos -e ansible _password=DevOps321'
      }
    }
  }
  post {
    always {
      cleanWs()
    }
  }
}