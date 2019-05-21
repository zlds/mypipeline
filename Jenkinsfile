pipeline {
	agent any
	stages {
		stage("SCM Checkout") {
			steps {
				withMaven(maven : "maven")
				sh 'mvn celan compile'
			}
		}
		stage("Testing Stage") {
			steps {
				withMaven(maven : 'maven')
				sh 'mvn test'
			}
		}
		stage("Deploy Stage") {
			steps {
				withMaven(maven : 'maven')
				sh 'mvn deploy'
			}
		}
	}

}
