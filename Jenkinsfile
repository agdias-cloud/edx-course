pipeline {
    agent {
        kubernetes {
            yaml 
            '''
            apiVersion: v1
            kind: Pod
            metadata:
              name: python-space
            spec:
              containers:
              - name: python-space
                image: python:3.9.19
                command:
                - cat
                tty: true
            '''
        }
    }
    stages {
        stage('install') {
            steps {
                container: ('python-space')
                sh 'pip install --upgrade pip && \
                pip install -r requirements.txt'
            }
        }
    }
}
