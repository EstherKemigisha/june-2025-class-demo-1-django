pipeline{
    agent any
    environment{
        VENV = 'venv'  
    }
    stages{
        stage('checkout') {
            steps{
                git branch: 'main', url: "https://github.com/EstherKemigisha/june25-classdemo2.git"
            }
        }
        stage('setup Virtual Environment') {
            steps{
                sh '''
                  python3 -m venv $VENV
                  . $VENV/bin/activate
                  pip install -r requirements.txt
                '''
            }
        }
        stage('run tests') {
            steps{
                sh '''
                  . $VENV/bin/activate
                  pytest
                '''
            }
        }
    }
}