#!groovy

node {
  // Establish some variables to be used throughout the script
  def environment
  
  stage('Checkout') {
    try {
      checkout scm
    } catch (error) {
      echo 'There was an error in the "Checkout" stage'
      throw error
    }
  }
  stage('Setup Environment') {
    try {
      if (env.BRANCH_NAME == 'master') {
        environment = 'production'
      } else if (env.BRANCH_NAME == 'qa') {
        environment = 'qa'
      } else if (env.BRANCH_NAME == 'staging') {
        environment = 'staging'
      } else {
        environment = 'development'
      }        
    } catch (error) {
      sh 'rm -Rf ./*'
      throw error
    }
  }
  stage('Linting') {
    try {
      echo "I'm on the Linting Stage for my ${environment} environment"
      // Run some linting commands
      echo 'Done'
    } catch (error) {
      sh 'rm -Rf ./*'
      throw error
    }
  }
  stage('Build') {
    try {
      echo "I'm on the Build Stage for my ${environment} environment"
      // Run some build commands
      echo 'Done'
    } catch (error) {
      sh 'rm -Rf ./*'
      throw error
    }
  }
  stage('Test') {
    try {
      echo "I'm on the Test Stage for my ${environment} environment"
      // Run some test commands
      echo 'Done'
    } catch (error) {
      sh 'rm -Rf ./*'
      throw error
    }
  }
  stage('Deploy') {
    try {
      echo "I'm on the Deploy Stage for my ${environment} environment"
      // Run some deploy commands
      echo 'Done'
    } catch (error) {
      sh 'rm -Rf ./*'
      throw error
    }
  }
  stage('Clean Up') {
    try {
      echo "I'm on the Clean Up Stage for my ${environment} environment"
      // Run some cleanup commands
      echo 'Done'
    } catch (error) {
      sh 'rm -Rf ./*'
      throw error
    }
  }
}
