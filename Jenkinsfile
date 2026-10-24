// Jenkins webhook test

pipeline 
    agent any 
    environment {
        CONTAIINER_NAME = "nestjs-app"
        IMAGE_NAME = "nestjs-image"
        EMAIL = "mmenterprises0@gmail.com"
        PORT = "3000" 
    }
    stages {
        stage ( 'clone repo' ) {
            steps {
                git branch: 'main', url: 'https://github.com/mazhar1976/cicd-pipeline-webhook-nestjs-app-automation-.git'
            }
        }
        stage ( 'Build Docker Image' ) {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }
        stage ( 'Stop & Remove Previous Container' ) {
            steps {
                sh ''' 
                docker stop $CONTAINER_NAME$ | |
                true
                dockr run $CONTAINER_NAME$ | | true
                '''
            }
        }
        stage ( 'Docker Container Run' ) {
            steps {
                sh ''' 
                docker run -d -p ${PORT}:${PORT}
                --name $CONTAINER_NAME $IMAGE_NAME
                '''
            }
        }
        stage ( 'Send Email Notification ' ) {
            steps {
                emailtext (
                    subject: "NestJS App Deloyed"
                    Successfully on EC2!"
                    body: "Your NestJS APP is Deployed...!"
                    http://"IP:PORT//" ,
                    to: "mmenterprises02@gmail.com"
                )
            }
        }
    }
}



