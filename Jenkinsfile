pipeline {
    agent any
    tools {
        jdk 'JAVA_HOME'
        maven 'MAVEN_HOME'
    }
    stages{
        stage('Maven-Build'){
            steps {
                 echo "Starting"
                 sh 'mvn clean package'
               }
          }
        stage('Docker-Build'){
            steps {
                sh "docker build -t webapp:${env.BUILD_ID} ."
            }
        }
        stage('Tagging-Docker-Image'){
            steps {
                sh 'docker login -u srahulgurnule -p Google@123#'
                sh "docker tag webapp:${env.BUILD_ID} srahulgurnule/webapp:${env.BUILD_ID}"
		
            }
        }
        stage('Pushing-Image-to-DockerHub'){
            steps {
                sh 'echo Pushed'
		sh "docker push srahulgurnule/webapp:${env.BUILD_ID}"        
            }
        }
    }
}   
