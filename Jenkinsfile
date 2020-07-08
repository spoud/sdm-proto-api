pipeline {
    agent {
        docker {
            label 'aws-t3-micro'
            image 'spoud/build:linux-generic'
            alwaysPull true
        }
    }
    options { buildDiscarder(logRotator(numToKeepStr: '5')) }

    stages {
        stage ('Compile proto file ') {
            steps {
                sh 'mkdir -p out/java out/docs'
                sh 'find . -name "*.proto" | xargs protoc --proto_path=. --doc_out=./out/docs --java_out=./out/java'
            }
        }

    }
}

