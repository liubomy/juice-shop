pipeline {
  agent any
  stages {
    stage('scan') {
      steps {
        sh "docker run -v ${WORKSPACE}:/src --workdir /src returntocorp/semgrep-agent:latest semgrep-agent --config p/ci --suppress-errors"
      }
    }
  }
}
