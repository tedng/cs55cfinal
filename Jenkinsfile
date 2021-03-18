pipeline {
    agent any

    stages{
        stage('deploy to S3'){
            steps{
                sh 'aws s3 cp public/index.html s3://mycs55cfinal'
                sh 'aws s3api put-object-acl --bucket mycs55cfinal --key index.html --acl public-read-write'
                sh 'aws s3 cp public/error.html s3://mycs55cfinal'
                sh 'aws s3api put-object-acl --bucket mycs55cfinal --key error.html --acl public-read-write'
            }
        }
    }
    post{
        always{
            cleanWs disableDeferredWipeout: true, deleteDirs: true
        }
    }

}
