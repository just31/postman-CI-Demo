node {
    stage('clean'){
      cleanWs()
    }
    stage('postman-CI'){
      git 'https://github.com/just31/postman-CI-Demo.git'
    }
    stage('Install Node Dependencies'){
      sh 'npm install'
    }
    stage('Install HTML reporter'){
      sh 'npm install newman-reporter-html'
    }
    stage('Run Tests'){
      sh 'npm run api-test'
    }
    stage('publishHTML Report'){
      publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'newman', reportFiles: '*0.html', reportName: 'HTML Report', reportTitles: ''])
    }
}
