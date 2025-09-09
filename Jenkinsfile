pipeline{
    agent{
        label 'docker'
    }
    stages{
        stage('build docker image'){
            steps{
                sh 'docker build -t mero:docker-reco -f Dockerfile .'
            }
        }
        stage('RUN TESTS'){
            steps{
                script{
                    env.DOCKER_BUILDKIT=1
                    sh'docker run -e CI=true mero:docker-reco npm test'
                }
            }
        }
    }
}