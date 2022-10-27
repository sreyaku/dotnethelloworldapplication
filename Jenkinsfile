pipeline{
   agent any
    stages{
        stage('gitclone'){
            agent any
            steps{
                git credentialsId: 'bc010765-2802-482d-8502-5f629f70228a', url: 'https://github.com/sreyaku/NodeApplication.git'
            }
        }

        stage('Dockerizing '){
            steps{
                bat '''
                docker container stop myapp
            docker container rm myapp
           docker build -t aspnetcoreapp .
            //docker run  --rm -d -p 80:8083 testimage:1.0
             docker run -d -p 8083:80 --name myapp aspnetcoreapp
            '''
        }
        }
         }
    }
