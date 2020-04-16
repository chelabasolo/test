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
       dir("C:/Users/rbanas2/Documents/NetBeansProjects/mavenproject13") {
            //sh "${mvnHome}/bin/mvn -B -DskipTests clean package"
            sh "${mvnHome}/bin/mvn -B -DskipTests clean install"
            
            
            //sh "mavenproject10-1.0-SNAPSHOT.jar"
            //cd 'target'
            //java -jar 'mavenproject10-1.0-SNAPSHOT.jar'
            
            stash includes: "target/*.jar", name: "mavenproject13-1.0-SNAPSHOT"
            //sh "java -jar mavenproject12-1.0-SNAPSHOT"
            
       }
         
       //dir("C:/Users/rbanas2/Documents/NetBeansProjects/mavenproject10/target") {
       //   sh "mavenproject10-1.0-SNAPSHOT.jar"
       //}
	} 
	stage('deploy') {
		//mtaBuild script: this
	    cloudFoundryDeploy script: this
        
	} 
}      