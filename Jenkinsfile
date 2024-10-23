pipeline {
    agent {
        label 'syncsense'
    }

    stages {
        stage('PreBuild') {
            steps {
                echo 'Hello, world!'
            }
        }

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
