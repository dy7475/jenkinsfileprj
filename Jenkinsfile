pipeline{
	agent any
	stages{
		stage("checkout code"){
			steps {	
			    script{
						checkout([$class: 'GitSCM', 
						branches: [[name: '*/master']], 
						doGenerateSubmoduleConfigurations: false, 
						extensions: [], 
						submoduleCfg: [], 
						userRemoteConfigs: [[credentialsId: 'mygit', url: 'https://github.com/dy7475/jenkinsfileprj.git']]])
		
			}}
		}
		stage("run build"){
			steps {	
			    script{
			    echo 'build';
			}}
		}

	}
	post('run helm') { 
		always {
			script{
 			//your code
			echo 'helm';
	}}}
}

