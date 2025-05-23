pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/your-username/your-repo.git'
            }
        }
        stage('Build') {
            steps {
                sh 'your-build-command' // e.g., 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'your-test-command' // e.g., 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                ssh_agent(['your-ssh-credentials-id---']) {
                    sh '''
                        scp -r * user@compute-engine-ip:/path/to/deploy/
                        ssh user@compute-engine-ip 'cd /path/to/deploy && ./start.sh'
                    '''
                }
            }
        }
    }
}
