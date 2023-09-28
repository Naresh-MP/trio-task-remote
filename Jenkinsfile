pipeline{
    agent any
    {
        stage ("Build the docker images "){
            steps {
                sh '''
                docker build -t --name mysql ./db
                echo "mysql image build - successfull"
                docker build -t --name flask-app ./flask-app
                echo "flask-app image build - successfull"
                docker build -t --name nginx ./nginx
                echo "ngnix image build - successfull"
                '''
            }
        }
        stage ("login and push"){
            steps {
                sh '''
                docker login -u nareshm5859 -p kezqyt-hondyx-5Rjru
                docker push mysql
                docker push flask-app
                docker push nginx
                '''
            }
        }
        stage ("logout"){
            steps {
                sh '''
                docker logout
                '''
            }
        }
    }
}