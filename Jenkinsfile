pipeline {
    agent any
    stages {
        stage('upload') {
            dir('./'){

            pwd(); //Log current directory

            withAWS(region:'us-west-2',credentials:'aws-static') {

                 def identity=awsIdentity();//Log AWS credentials

                // Upload files from working directory 'dist' in your project workspace
                s3Upload(bucket:"udacitystaticcseah", workingDir:'', includePathPattern:'**/*');
            }

            };
        }
    }
}