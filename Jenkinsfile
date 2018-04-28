pipeline {
    agent any

    stages {
        stage('Unit Test') {
            sh ‘ant’
            junit ‘reports/*.xml’

        }
    }
}
