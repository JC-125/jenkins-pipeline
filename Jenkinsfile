pipeline {
	agent any
	stages {
		stage('compile Stage'){
			steps {
			 withMaven(maven : 'maven_3.6.3'){
					sh 'mvn clean compile'
			}}
		}
		
		stage('Deployment Stage'){
			steps{
			 withMaven(maven : 'maven_3.6.3') {
					sh 'mvn clean deploy -DmuleDeploy -DskipTests -Dmule.version=4.3.0 -Danypoint.username=praveen_TMC -Danypoint.password=QWERasdf1234 -Denv=Sandbox -Dappname=Jekins-pipeline -Dbusiness=TechMatrix-Sandbox -DvCore=Micro -Dworkers=1'
			}
		}
	}
	
	}
}