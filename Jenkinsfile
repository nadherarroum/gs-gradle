node {
  def myGradleContainer = docker.image('gradle:jdk8-alpine')
  myGradleContainer.pull()
  stage('prep') {
    checkout scm
  }
  stage('test') {
     myGradleContainer.inside("-v C:/Users/ING-Nadher/.gradle:/home/gradle/.gradle") {
       bat 'cd complete && gradle test'
     }
  }
  stage('run') {
     myGradleContainer.inside("-v C:/Users/ING-Nadher/.gradle:/home/gradle/.gradle") {
       bat 'cd complete && gradle run'
     }
  }
}
