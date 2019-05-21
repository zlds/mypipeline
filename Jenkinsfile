pipeline {
	agent any
	environment {
		def MvnHome = tool name: 'maven', type: 'maven'
        def MvnCMD = "${MvnHome}bin/mvn"
	}
	stages {
		stage("SCM Checkout") {
			steps {
				sh "${MvnCMD} celan compile"
			}
		}
		stage("Testing Stage") {
			steps {
				sh "${MvnCMD} mvn test"
			}
		}
		stage("Deploy Stage") {
			steps {
				sh "${MvnCMD} mvn deploy"
			}
		}
	}

}
