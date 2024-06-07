pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "test" >> test.txt'
                sh 'curl -H "Content-Tpe=text/plain&Content-Length=5" -d  " test.txt" -X POST https://www.googleapis.com/upload/drive/v3/files?uploadType=media'
                sh 'platform-tools/adb connect 172.16.9.181'
                sh '.maestro/bin/maestro test inrange-fe-testing-maestro/inbay-inrange/run-test.yml'
            }
        }
    }
    post {
        always {
            archiveArtifacts '*.png'
        }
    }
}
