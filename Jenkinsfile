pipeline{
  agent any

//  options{
//    ansiColor('xterm')
//  }

 environment {
    SSH = credentials('SSH')
 }
 stages{

   stage('Check Ansible Style Checks') {
   when{ expression pattern: "ROB-.*",comparator: "REGEXP"}
    steps {
      echo "Ansible Style Checks"
    }
   }

   stage('Run Ansible in Sandbox Environment') {
   when{ expression pattern: "PR-.*",comparator: "REGEXP"}
       steps {
         sh '''
            ansible-playbook roboshop-check.yml -e role_name=frontend -e ansible_username=centos -e ansible_password=DevOps321 -e ENV=sandbox -e CHECK_MODE=true
         '''
       }
      }

    stage('Promote code to PROD branch') {
     when{ branch  'main'}
        steps {
          sh 'env'
          sh 'echo MAIN'
        }
        }

}
}