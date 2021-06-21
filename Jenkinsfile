pipeline {
    agent {
        docker {
            label 'aws-t3-micro'
            image 'spoud/build:linux-generic'
        }
    }

    stages {
        stage ('Compile proto file ') {
            steps {
                sh 'mkdir -p out/java out/docs'
                sh 'find . -name "*.proto" | xargs protoc --proto_path=$GOPATH/src/github.com/gogo/protobuf/protobuf --proto_path=. --doc_out=./out/docs --java_out=./out/java'
            }
        }
    }
}

