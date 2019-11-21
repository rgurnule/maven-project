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
                sh 'docker login -u satyendrasing -p Password@123'
                sh "docker tag webapp:${env.BUILD_ID} satyendrasing/webapp:${env.BUILD_ID}"
		sh "docker push satyendrasing/webappp:${env.BUILD_ID}"
            }
        }
        stage('Pushing-Image-to-DockerHub'){
            steps {
                sh 'echo Pushed'
		        
            }
        }
    }
}   
