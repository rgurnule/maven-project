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
    }
}   
