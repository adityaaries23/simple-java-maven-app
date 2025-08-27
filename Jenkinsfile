node {
  // caches your Maven repo for speed; adjust path on Windows/WSL if needed
  docker.image('maven:3.9-eclipse-temurin-21').inside('-p 3000:3000') {
    stage('Build') { sh 'mvn -B -DskipTests clean package' }
    stage('Test') {sh 'mvn test'}
  }
}