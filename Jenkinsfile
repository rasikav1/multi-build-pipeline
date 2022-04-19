pipeline {
    agent any
    tools {
        maven "localmaven"
    }
    stages {
        stage('SCM Checkout'){
            steps{
                git branch: 'main', credentialsId: 'f8f917fc-1e0c-49ce-ba31-5424ea5ee2d7', url: 'https://github.com/rasikav1/mavenproject1.git'
            }
        }
        stage('MVN Build'){
            steps{
                sh "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }
        stage('MVN test'){
            steps{
                sh "mvn test"
            }
        }
        stage('test report'){
            steps{
                junit 'target/surefire-reports/*.xml'
            }
        }
    }
}
