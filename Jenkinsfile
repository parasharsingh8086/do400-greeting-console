pipeline{
    agent{
        label "nodejs"
    }
    stages{
        stage("Install dependencies"){
            steps{
                sh "npm ci"
            }
        }

        stage("Check Style"){
            steps{
                sh "npm run lint"
            }
        }

        stage("Test"){
            steps{
                sh "npm test"
            }
        }
        
        stage('Release'){
            steps {
                sh '''
                   oc project parasharsingh8086-greetings
                   oc start-build greeing-console --follow --wait
                '''   
            }
        }

        // Add the Release stage here
    }
}
