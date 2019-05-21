pipeline {
	agent any
	environment {
		def MvnHome = tool name: 'maven', type: 'maven'
        def MvnCMD = "${MvnHome}bin/mvn"
	}
	stages {
		stage("SCM Checkout") {
			steps {
				sh "${MvnCMD} clean compile"
			}
		}
		stage("Testing Stage") {
			steps {
				sh "${MvnCMD} test"
			}
		}
		stage("Deploy Stage") {
			steps {
				sh "${MvnCMD}  clean package"
			}
		}
	}

}
