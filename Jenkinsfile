pipeline {
    agent ecs-agent

    stages {
        stage('Install dependencies') {
            steps {
                sh('npm install')
                sh('npm install --global gulp')
            }
        }
        stage('Testing') {
            steps {
                echo 'Testing...'
                sh 'npm test'
            }
        }
        stage('Publishing') {
            steps {
                echo 'zipping artifact'
                sh 'tar -czf /tmp/ssfdata.tar.gz .'
                //echo 'publishing to s3 bucket'
            }
        }
        stage('Terraform') {
            steps {
                echo 'creating new Elastic Beanstalk version'
            }
        }
        stage('Deploy') {
            steps{
                echo 'eb deploy...'
            }
        }
    }
}
