pipeline{
  agent any

 options{
   ansiColor('xterm')
 }

 environment {
    ssh = credentials('SSH')
 }

  stages('Do a Dry Run'){
  //Here we are hardcoding role name as frontend as for demo purpose,but we need to understand which role has been really modified and we need to parse that role name,
  //we can get that info from git commands,Here it is example. git diff HEAD@{1} --name-only | grep roles | awk -F /  '{print $2}'
  steps {
  sh '''
    ansible-playbook roboshop-check.yml -e role_name=frontend -e ansible_username=centos -e ansible_password=DevOps321 -e ENV=sandbox
  '''
  }
  }
}