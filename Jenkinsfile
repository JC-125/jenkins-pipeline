pipeline {
	agent any
	stages {
		stage('compile Stage'){
			steps {
					bat  'mvn clean compile'
			}
		}
		
		stage('Deployment Stage'){
			steps {
					bat  'mvn clean deploy -DmuleDeploy -DskipTests -Dmule.version=4.3.0 -Danypoint.username=praveen_TMC -Danypoint.password=QWERasdf1234 -Denv=Sandbox -Dappname=Jekins-pipeline -Dbusiness=TechMatrix-Sandbox -DvCore=Micro -Dworkers=1'
			}
		}
	}
	
	
        stage('Ok') {
            steps {
                echo "Ok"
            }
        }
    
    post {
        always {
            emailext body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'
        }
    }
}
