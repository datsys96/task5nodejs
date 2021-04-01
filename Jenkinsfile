pipeline {
     agent { label 'jenkinslave' }
     stages {
          stage("clone code") {
               steps {
                    git 'https://github.com/datsys96/task5nodejs.git'
               }
          }
          stage("build image") {
               steps {
                    sh 'docker build -t nodejs1:1 .'
               }
          }
     }
}
