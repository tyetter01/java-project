pipeline {
    agent any

    stages {
        stage('Unit Tests') {
            steps {
                sh 'ant -f test.xml -v'
                junit 'reports/result.xml'
            }
        }
        stage('Build'){
            steps {
                sh 'ant -f build.xml -v' 
            }
        }
        stage('Deploy'){
            steps{
                sh 'aws s3 cp var/jenkins_home/workspace/java-pipeline/rectangle-${BUILD_NUMBER}.jar s3://tyetter01-test-bucket/rectangle-${BUILD_NUMBER}.jar'
            }
        }
    }
}
