pipeline {
    agent { label 'ansible' }
    stages{
      stage	('get some code on git hub'){
         steps {    
        git 'https://github.com/gangu-git/spring-framework-petclinic.git'
      }
    }
      stage ('excuting mvn comands'){
        steps { 
            sh 'mvn compile'
       }
   }
       stage ('excuting mvn test command'){
	   steps {
	        sh 'mvn test'
			}
		}
       stage ('excuting mvn package command'){
        steps{
             sh 'mvn package'
          }
        }		  
  }
}
