@Library('piper-lib-os') _
node() {
	stage('build') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }
    stage('test') {
        //mtaBuild script: this
        //def mvn_version = 'M3'
        //dir("C:/Users/rbanas2/Documents/NetBeansProjects/mavenproject10") {
        //  sh "mvn clean install"
       //}
       
       def mvnHome = tool name: 'M3', type: 'maven'
       dir("C:/Users/rbanas2/Documents/NetBeansProjects/mavenproject10") {
            //sh "${mvnHome}/bin/mvn -B -DskipTests clean package"
            sh "${mvnHome}/bin/mvn -B -DskipTests clean install"
            sh "mavenproject10-1.0-SNAPSHOT.jar"
       }
       
       //dir("C:/Users/rbanas2/Documents/NetBeansProjects/mavenproject10/target") {
       //   sh "mavenproject10-1.0-SNAPSHOT.jar"
       //}
	} 
	stage('deploy') {
	    cloudFoundryDeploy script: this
	}
}      