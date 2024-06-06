pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'platform-tools/adb connect 172.16.9.181'
                sh 'cd inrange-fe-testing-maestro/inbay-inrange'
                sh 'time maestro test run-test.yml'
            }
        }
    }
}
