pipeline {
    agent any
    stages {
        stage('Check Gradle Wrapper') {
            steps {
                sh 'pwd'
                sh 'ls -al'
            }
        }
        stage("Prepare Gradlew") {
            steps {
                // gradlew 파일 존재 여부 확인
                sh '''
                if [ ! -f gradlew ]; then
                  echo "gradlew 파일이 없습니다. 먼저 gradle wrapper를 추가하세요!"
                  exit 1
                fi
                chmod +x gradlew
                '''
            }
        }
        stage("Compile") {
            steps {
                sh "./gradlew compileJava"
            }
        }
        stage("Build") {
            steps {
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