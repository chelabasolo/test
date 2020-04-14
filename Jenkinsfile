@Library('piper-lib-os') _
node() {
    stage('build') {
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