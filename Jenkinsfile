node {
    docker.image('node:16-buster-slim').withRun('-p 3000:3000') {
        
        // Tahap Build
        stage('Build') {
            tool 'nodejs'
            sh 'npm install'
        }
        
        // Tahap Test
        stage('Test') {
            sh './jenkins/scripts/test.sh'
        }

        // Tahap Deploy
        stage('Deploy') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Sudah selesai menggunakan React App? (Klik "Proceed" untuk mengakhiri)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
