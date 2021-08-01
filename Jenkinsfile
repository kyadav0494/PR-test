pipeline {
    agent any
    stages{
    	stage('checkout'){
    		steps{
    			checkout([$class: 'GitSCM',
          			doGenerateSubmoduleConfigurations: false,
          			extensions: [[$class: 'SubmoduleOption',
                   	    disableSubmodules: false,
                   	    parentCredentials: false,
                       	recursiveSubmodules: true,
                       	parentCredentials: true,
                       	reference: '',
                       	trackingSubmodules: false]], 
          			submoduleCfg: [], 
          			userRemoteConfigs: [[credentialsId: "kapil-test", url: 'https://git.aa.st/c-kapyad/kapil-test']]])
    		}
		stage('build'){
			steps{
				mvn clean
				mvn validate
				mvn install
			}
		}	
    	}
    }
}
