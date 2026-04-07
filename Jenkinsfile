pipeline {
  agent any 
  stages{
    stage('#1. Checkout'){
      steps{
        git url: 'https://github.com/CoderSohail2003/Docker47.git', branch: 'main'
      }
    }

    stage('#2. Build the image'){
      steps{
        bat 'docker build -t mywebsiterepo .'
      }
    }

    stage('#3. Stop all old containers'){
      steps{
        bat 'docker stop mycont || exit 0'
        bat 'docker rm mycont || exit 0'
      }
    }

    stage('#4. Run the image - Containerise'){
      steps{
        bat 'docker run -d -p 4000:80 --name mycont mywebsiterepo'
      }
    }
  }
}
