node {
  // caches your Maven repo for speed; adjust path on Windows/WSL if needed
  def m2 = "${env.HOME}/.m2"
  docker.image('maven:3.9-eclipse-temurin-17').inside("-v ${m2}:/root/.m2") {
    stage('Build') { sh 'mvn -B -DskipTests clean package' }
  }
}