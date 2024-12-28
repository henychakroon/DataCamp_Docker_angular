pipeline {
agent any
tools{ jdk 'JDK17' }
environment {
JAVA_HOME ='C:\\Program Files\\Java\\jdk-17'
DOCKER_TAG = getVersion()
}
stages {
stage ('Clone Stage') {
steps {
git branch: 'main', url: 'https://github.com/henychakroon/DataCamp_Docker_angular.git'
}
}
stage ('Docker Build') {
steps {
bat 'docker build -t henychakroon/aston-villa:${DOCKER_TAG} .'
}
}
}
}

  def getVersion() {
    def version = bat(script: 'git rev-parse --short HEAD', returnStdout: true).trim()
    return version
}
