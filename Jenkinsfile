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
git https://github.com/henychakroon/DataCamp_Docker_angular.git'
}
}
stage ('Docker Build') {
steps {
sh 'docker build -t henychakroon/aston-villa:${DOCKER_TAG}.'
}
}
}
}
#def getVersion(){
#def version = sh returnStdout: true, script: 'git rev-parse --short HEAD'
#return version
#}
  def getVersion() {
    def version = bat(script: 'git rev-parse --short HEAD', returnStdout: true).trim()
    return version
}
