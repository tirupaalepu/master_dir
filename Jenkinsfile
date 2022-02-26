pipeline {
  agent any
  environment {
   ANSIBLE_PRIVATE_KEY=credentials('private-key') 
  }
  stages {
    stage('Hello') {
      steps {
        sh 'ansible-galaxy collection install -r requirements.yml'
        sh 'ansible-playbook -i dev.inv --private-key=$ANSIBLE_PRIVATE_KEY get-uptime.yaml'
      }
    }
  }
}
