pipeline {
    agent any
    tools {
        jdk 'JAVA_HOME'
        maven 'MAVEN_HOME'
    }
    stages{
        stage('Build'){
            steps {
                  echo "Starting"
                  bat label: '', script: 'mvn clean package'
                  bat label: '', script: '"docker build -t webapp:${env.BUILD_ID} ."'

            }
        }
    }
}
