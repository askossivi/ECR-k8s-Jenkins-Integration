///Jenkinsfile = '/var/jenkins_home/jobs/Jenkins-Image-Job'
///docker_file_dir = '/var/jenkins_home/jobs/Jenkins-Image-Job'

pipeline {
  environment {
    registry = '111122718813.dkr.ecr.us-east-2.amazonaws.com/askossivi'
    registryCredential = 'Jenkins_ECR_Login'
    dockerImage = ''
  }
  agent any
  stages {
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
    stage('Deploy image') {
        steps{
            script{
                docker.withRegistry("https://" + registry, "ecr:us-east-2:" + registryCredential) {
                    dockerImage.push()
                }
            }
        }
    }
  }
}
