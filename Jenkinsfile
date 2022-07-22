pipeline {
  agent any
  stages {
    stage('Init') {
      steps {
        echo 'Initializing..'
        echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
        echo "Current branch: ${env.BRANCH_NAME}"
        sh 'echo $DOCKER_PASSWORD | docker login -u $DOCKER_ID --password-stdin'
      }
    }

    stage('Test') {
      steps {
        echo 'Testing..'
        echo 'Running pytest..'
        sh 'java -version'
      }
    }

    stage('Build') {
      steps {
        echo 'Building..'
        echo 'Running docker build -t sntshk/cotu .'
      }
    }

    stage('Publish') {
      steps {
        echo 'Publishing..'
        echo 'Running docker push..'
      }
    }

    stage('Cleanup') {
      steps {
        echo 'Cleaning..'
        echo 'Running docker rmi..'
      }
    }

  }
  environment {
    DOCKER_ID = credentials('DOCKER_ID')
    DOCKER_PASSWORD = credentials('DOCKER_PASSWORD')
  }
}