node {
  docker.image('maven:latest').inside('-p 3000:3000') {
    stage('Checkout') { git 'https://github.com/adityaaries23/simple-java-maven-app.git' }
    stage('Build') { sh 'mvn -B -DskipTests clean package' }
    stage('Test') {sh 'mvn test'}
    stage('Manual Approval') {
      input message: 'Lanjutkan ke tahap Deploy?', ok: 'Proceed'
    }
    stage('Deploy') {
        sh './jenkins/scripts/deliver.sh'
    }
  }
}