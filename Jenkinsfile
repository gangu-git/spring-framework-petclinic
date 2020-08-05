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
            stage (' uploding artifact on aws s3 bucket'){
               steps{
                      s3Upload 'consoleLogLevel: 'INFO', dontSetBuildResultOnFailure: false, dontWaitForConcurrentBuildCompletion: false, entries: [[bucket: 's3artifactdemog', excludedFile: '/target/', flatten: false, gzipFiles: false, keepForever: false, managedArtifacts: false, noUploadOnFailure: false, selectedRegion: 'us-west-2', showDirectlyInBrowser: false, sourceFile: '**/target/*.war', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: false]], pluginFailureResultConstraint: 'FAILURE', profileName: 's3fulljenkins', userMetadata: []'
               }
            }              
    
    }
}
