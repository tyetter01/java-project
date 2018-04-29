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
                sh 'aws s3 cp /workspace/java-pipeline/dist/rectangle-${BUILD_NUMBER}.jar s3://tyetter01-test-bucket/'
            }
        }
        stage('Report'){
            steps{
                sh 'aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins'
            }
        }
    }
}
