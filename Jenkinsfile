pipeline{
	agent any
	stages{
	    stage('checkout'){
			steps {	
			    script{
			    echo 'build';
				checkout scm
			}}
        
        
		}
		stage('Prepare') {
			
			steps {	
			script {
				build_tag = sh(returnStdout: true, script: 'git rev-parse --short HEAD').trim()
				if (env.BRANCH_NAME != 'master') {
					build_tag = "${env.BRANCH_NAME}-${build_tag}"
				}
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

