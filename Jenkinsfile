pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'platform-tools/adb connect 172.16.9.181'
                sh '.maestro/bin/maestro test inrange-fe-testing-maestro/inbay-inrange/run-test.yml'
                step([$class: 'ClassicUploadStep', credentialsId: env.GDA, bucket: "gs://${env.BUCKET}, pattern: env.PATTERN"])
            }
        }
    }
    post {
        always {
            archiveArtifacts '*.png'
        }
    }
}
