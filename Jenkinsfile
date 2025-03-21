@Library("shared") _
pipeline{
    agent any;
    stages{
        stage("clean workspace"){
            steps{
                script{
                   clean_worspace()
                }
            }
        }
    
        stage("Code"){
            steps{
                script{
                    clone("https://github.com/SnehaSanam/django-notes-app.git", "devops")
                }
            }
        }
        stage("Build"){
            steps{
                script{
                    docker_build("django-notes-app", "latest", "snehasanam" )
                }
            }
        }
        stage("Push to Dockerhub"){
            steps{
                script{
                    docker_push("django-notes-app", "latest", "snehasanam")
                }
            }
        }
        stage("Deploy"){
            steps{
                script{
                    docker_compose()
                }
                }
            }
        }
}
