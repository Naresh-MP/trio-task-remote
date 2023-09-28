pipeline {
    agent any
    stages {
        stage ("Build the docker images "){
            steps {
                sh '''
                docker build -t nareshm5859/mysql ./db
                echo "mysql image build - successfull"
                docker build -t nareshm5859/flask-app ./flask-app
                echo "flask-app image build - successfull"
                docker build -t nareshm5859/nginx ./nginx
                echo "ngnix image build - successfull"
                '''
            }
        }
        stage ("Push"){
            steps {
                sh '''
                docker push nareshm5859/mysql
                docker push nareshm5859/flask-app
                docker push nareshm5859/nginx
                '''
            }
        }
    }
}