pipeline {
  agent any
  stages {
    stage('scan') {
      steps {
        sh "docker run -v ${WORKSPACE}:/src --workdir /src returntocorp/semgrep-agent:latest semgrep-agent --config p/ci --config p/security-audit --config p/secrets | tee -a semgrep.txt"
        archiveArtifacts artifacts: 'semgrep.txt', followSymlinks: false
      }
    }
  }
}
