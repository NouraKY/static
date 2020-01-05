pipeline {
    agent any
    stages {
        stage('Upload to AWS'){
            steps {
               withAWS(region:'us-west-2', credentials:'jenkins') {
                   
                   s3Upload(file:'/index.html', bucket:'jenkinspipline', path:'/')
               }
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
}
