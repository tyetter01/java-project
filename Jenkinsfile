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
                sh 'aws s3 cp s3://tyetter01-test-bucket/ --include "rectangle-*.jar"'
            }
        }
    }
}
