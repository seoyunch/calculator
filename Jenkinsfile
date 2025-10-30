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
        stage('Check Gradle Wrapper') {
            steps {
                sh 'pwd'          // 현재 디렉토리 출력
                sh 'ls -al'       // gradlew 파일 있는지 확인
            }
        }
    }
}