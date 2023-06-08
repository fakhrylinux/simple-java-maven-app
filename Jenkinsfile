Node {
    docker.image('maven:3.9.0').inside('-p 3000:3000 -v /root/.m2:/root/.m2') {
        stage('Build') {
            checkout scm
            sh 'mvn -B -DskipTests clean package'
        }
        stage('Test') {
            sh 'mvn test'
        }
    }
}