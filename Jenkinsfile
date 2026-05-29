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

        cd /var/lib/jenkins/workspace/firstPipeline

        pm2 restart myapp || pm2 start index.js --name myapp

        pm2 save
                

                '''

            }
        }
    }
}