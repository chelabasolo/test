@Library('piper-lib-os') _
node() {
    stage('build') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }
    stage('test') {
        if (isUnix()) --> sh "command"
        else --> bat "command"
	    mtaBuild script: this
	}
	stage('deploy') {
	    cloudFoundryDeploy script: this
	}
}           