pipeline{
   agent any
    stages{
        stage('gitclone'){
            agent any
            steps{
                git credentialsId: 'bc010765-2802-482d-8502-5f629f70228a', url: 'https://github.com/sreyaku/dotnethelloworldapplication.git'
            }
        }

        stage('Dockerizing '){
            steps{
                bat '''
                docker container stop myapp
            docker container rm myapp
           docker build -t aspnetcoreapp .
           docker run -d -p 80:80 --name myapp aspnetcoreapp
          
            '''
        }
        }
         }
    }
