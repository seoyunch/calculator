pipeline {
    agent any
    stages {
        stage("Compile") {
            steps {
                sh "./gradlew compileJava"
            }
        }

        stage("Build") {
            steps {
                sh "chmod +x gradlew"
                sh "./gradlew build"
            }
        }

        stage("Unit test") {
            steps {
                sh "./gradlew test"
            }
        }
    }
}