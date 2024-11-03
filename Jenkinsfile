@Library("Shared") _

pipeline{
    agent {label "foysal"}
    
    stages {
        stage("Hello"){
             steps{
                 script{
                     hello()
                 }
             }
        }
        stage("Code pull"){
            steps{
                script{
                    git_clone("https://github.com/devFoysal/django-notes-app.git", "main")
                }
            }
        }
        stage("Build"){
            steps{
                script{
                    docker_build("notes-app", "latest", "foysalmahmud68")
                }
            }
        }
        stage("Push to DockerHub"){
            steps{
                script{
                    docker_push("notes-app", "latest", "foysalmahmud68")
                }
            }
        }
        stage("Delploy"){
            steps{
                script{
                    docker_compose()
                }
            }
        }
    }
}
