pipeline {
    agent any 
    
    stages{
        stage("Clone Code"){
            steps {
                echo "Clon the code"
                git url:"https://github.com/mendhe1020/django-notes-app.git", branch: "main"    
            }
        }
        stage("Build"){
            steps {
                echo "Building the image"
                sh "docker build -t my-note-app ."
                sh "docker run -it -d my-note-app"
            }
        }
        stage("Deploy"){
            steps {
                echo "Deploying the container"
                sh "docker-compose down && docker-compose up -d"
                
            }
        }
    }
}
