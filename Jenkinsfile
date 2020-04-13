@Library('piper-lib-os') _
node() {
    stage('code') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }
    stage('test') {
	    mtaBuild script: this
	}
	stage('deploy') {
	    cloudFoundryDeploy script: this
	}
}     