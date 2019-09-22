pipeline {
    agent any        
        stages {
        stage('Build') {
            steps {
                sh 'mvn clean install' 
                sh 'mvn -B -DskipTests package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit '/var/lib/jenkins/workspace/E2E_maven_pipeline/target/surefire-reports/*.xml'
                }
            }
        }
      /*  stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        } */
    }
}
