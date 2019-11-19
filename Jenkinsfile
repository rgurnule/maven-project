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
                  bat lable: '', script: 'mvn clean package'
            }
        }
    }
}
