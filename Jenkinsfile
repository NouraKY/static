pipeline {
    agent any
    stages {
        stage('Lint HTML'){
            steps{   
                 ssh 'tidy -q -e *.html'   
                
            }
        }
        
        stage('Upload to AWS'){
            steps {
               withAWS(region:'us-west-2', credentials:'aws-static') {
                   
                   s3Upload(file:'index.html', bucket:'jenkinspipline', path:'/')
               }
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
}
