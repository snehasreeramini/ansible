pipeline{
  agent any

  stages('Do a Dry Run'){
  steps {
  sh '''
    ansible-playbook roboshop.yml -e HOST=localhost -e role_name=frontend -C -b
  '''
  }
  }

}