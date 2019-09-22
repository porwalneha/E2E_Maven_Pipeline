pipeline {
    agent any        
        stages {
        stage('Build') {
            steps {
                
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            /* post {
                always {
                    junit '/var/lib/jenkins/workspace/E2E_maven_pipeline/target/surefire-reports/*.xml'
                } 
            } */
        }
      /*  stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        } */
            stage('Deploy')
            steps {
                  {
                      sh 'mvn clean deploy'
                  }
            }
                   
                      
    }
}
