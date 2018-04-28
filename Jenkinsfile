pipeline {
    agent any

    stages {
        stage('Unit Tests') {
            steps {
                sh 'ant -f test.xml -v'
            }
            steps {
                junit ‘reports/result.xml’
            }
        }
    }
}
