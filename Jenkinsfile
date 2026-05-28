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

        stage('Build Stage') {

            steps {

                sh 'npm install'

            }
        }
        stage('Deploy Stage') {

            steps {

                sh '''

                /usr/local/bin/pm2 delete myapp || true

                /usr/local/bin/pm2 start index.js --name myapp

                /usr/local/bin/pm2 save

                '''

            }
        }
    }
}