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

        stage('Build') {
            steps {
                dir('hello-world') {
                    sh 'uname -a'
                    sh 'env'
                    sh 'source /home/jenkins/nvm.sh'
                    sh 'npm install'
                    sh 'ng build --prod'
                }
            }
        }

        stage('Deploy') {
            steps {
                sh 'cp -r hello-world/dist/* /output'
            }
        }
    }
}
