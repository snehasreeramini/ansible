pipeline {
   agent any

 options {
    ansiColor('xterm')
 }

 environment {
    SSH = credentials('SSH')
 }

   stages('MAIN'){
   when { branch 'main' }
         steps{
         sh '''
           env
           '''
         }
      }
   }
 }