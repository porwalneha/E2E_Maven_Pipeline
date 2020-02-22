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
        }
            /* post {
                always {
                    junit '/var/lib/jenkins/workspace/E2E_maven_pipeline/target/surefire-reports/*.xml'
                } 
            } */
        
      /*  stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        } */
            stage('Deploy') {
            steps {
              withCredentials([file(credentialsId: 'admin', variable: 'settings')]) {
    // some block

    // some block
    sh 'mvn -s settings.xml deploy'
    /*  sh 'mvn deploy:deploy-file -DpomFile=pom.xml -Dfile=target/my-app-1.0.jar -Durl=http://18.218.83.190:8081/nexus/content/repositories/releases/' */
                  }
            }
            }
                   
                      
    }
}
