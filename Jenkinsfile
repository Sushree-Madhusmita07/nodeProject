// pipeline {
//     agent any
//     stages {
//         stage('Build') {
//             steps {
//                 sh 'npm install'
//             }
//         }
//         stage('Test') {
//             steps {
//                 sh 'node index.js'
//             }
//         }
//     }
// }



pipeline {
    agent any

    stages {

        stage('Clean') {
            steps {
                deleteDir()
            }
        }

        stage('Clone') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Sushree-Madhusmita07/nodeProject.git'
            }
        }

        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                pm2 delete myApp || true
                pm2 start index.js --name myApp
                pm2 save
                '''
            }
        }
    }
}