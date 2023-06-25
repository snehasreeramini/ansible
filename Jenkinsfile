pipeline {
   agent any

 options {
    ansiColor('xterm')
 }

 environment {
    SSH = credentials('SSH')
 }

   stages{
      stage{ ('Test')
         steps{
         sh '''
           env
           '''
         }
      }
   }
 }