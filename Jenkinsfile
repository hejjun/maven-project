// pipeline {
//     agent any
//     stages{
//         stage('Init'){
//             steps {
//                 echo "Testing......"
//             }
//         }
//  	stage('Build'){
//             steps {
//                 echo "Building......"
//             }
//         }
//  	stage('Deploy'){
//             steps {
//                 echo "Code Deployed."
//             }
//         }
//     }
// }

pipeline {
    agent any
    tools {
        maven "local maven"
        jkd "local jkd"
    }
    stages{
        stage('Build'){
            steps {
                sh "mvn clean package"
            }
            post {
                success {
                    echo "开始存档......"
                    archiveArtifacts artifacts: "**/target/*.war"
                }
            }
        }
    }
}