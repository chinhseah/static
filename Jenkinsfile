pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {

                pwd(); //Log current directory

                withAWS(region:'us-west-2',credentials:'aws-static') {

                    def identity=awsIdentity();//Log AWS credentials

                    // Upload files from current directory in your project workspace
                    s3Upload(bucket:"udacitystaticcseah", workingDir:'', includePathPattern:'**/*');
                }

            };
        }
    }
}