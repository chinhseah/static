pipeline {
    agent any
    stages {
        stage('Lint HTML'){
            steps {
                sh 'tidy -q -e *.html'
            };
        }
        stage('Upload to AWS') {
            steps {

                pwd(); //Log current directory

                withAWS(region:'us-west-2',credentials:'jenkins') {

                    // Upload files from current directory in your project workspace
                    s3Upload(file:'index.html', bucket:'udacitystaticcseah', path:'')
                }

            };
        }
    }
}