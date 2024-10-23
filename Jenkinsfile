pipeline {
    agent any

    stages {
        // stage('Checkout') {
        //     steps {
        //         checkout scm {
        //             git {
        //                 url 'https://your-git-repository-url.git' // Replace with your Git repository URL
        //                 credentials 'your-credentials-id' // Replace with your credentials ID
        //             }
        //         }
        //     }
        // }

        stage('Build') {
            steps {
                dir('hello-world') {
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