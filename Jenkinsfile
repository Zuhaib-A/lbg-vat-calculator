pipeline {
  agent any

  stages {
    stage('Checkout') {
        steps {
          // Get some code from a GitHub repository
          git branch: 'main', url: 'https://github.com/Zuhaib-A/lbg-vat-calculator.git'
        }
    }
    stage('SonarQube Analysis') {
      environment {
        scannerHome = tool 'sonar-qube-1'
      }
        steps {
            withSonarQubeEnv('sonarqube') {        
              sh "${scannerHome}/bin/sonar-scanner"
            }   
        }
    }
  }
}