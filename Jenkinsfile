pipeline {
    agent any
    
    tools{
        maven "M3"
    }
    
    stages{
        //stage('Github'){
           // steps{
               // git branch: 'main', changelog: false, poll: false, url: 'https://github.com/vaheethraj/jenkins-hello-world.git'
           // }
        //}
        
        stage('Build'){
            steps{
                sh 'echo Building Package'
                sh 'mvn clean package -DskipTests'
            }
        }

	stage('Archive') { 
            steps{ 
                archiveArtifacts artifacts: 'target/hello-demo-*.jar', followSymlinks: false
	    }

	}

	stage('Test'){
           steps{ 
               sh 'mvn test'
	   }  

	}
    }
}
