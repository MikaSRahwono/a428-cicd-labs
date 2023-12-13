node {
    docker.image('node:16-buster-slim').withRun('-p 3000:3000') {
        
        // Tahap Build
        stage('Build') {
            sh 'npm install'
        }
        
        // Tahap Test
        stage('Test') {
            sh './jenkins/scripts/test.sh'
        }
    }
}
