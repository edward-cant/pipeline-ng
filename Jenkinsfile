pipeline {
    agent {
        label "syncsense"
    }

    stages {
        // stage('Checkout') {
        //     steps {
        //         checkout scm {
        //             git {
        //                 url 'https://github.com/edward-cant/pipeline-ng' 
        //             }
        //         }
        //     }
        // }
        
        stage('Information') {
            steps {
                sh 'ip a'
                sh 'uname -a'
                sh 'env'
                sh 'echo $PATH'
                sh 'which npm'
                sh 'which ng'
            }
        }

        stage('Build') {
            steps {
                dir('hello-world') {
                    sh 'npm install'
                    sh 'ng build'
                }
            }
        }

        stage('Deploy') {
            steps {
                sh 'mkdir -p output/'
                sh 'cp -r hello-world/dist/* output/'
            }
        }
    }
}
