@Library('piper-lib-os') _
node() {
    stage('build') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }
    stage('test') {
        //mtaBuild script: this
        //dir("mavenproject11") {
        //  sh "mvn clean install"
       //}
       dir("mavenproject11/target") {
          sh "mavenproject11-1.0-SNAPSHOT.jar"
       }
	}
	stage('deploy') {
	    cloudFoundryDeploy script: this
	}
}  