pipeline {
     agent { label 'jenkinslave1' }
     stages {
          stage("clone code") {
               steps {
                    git 'https://github.com/datsys96/task5nodejs.git'
               }
          }
          stage("build image") {
               steps {
                    sh 'docker build -t nodejs12:2 .'
               }
          }
     }

    post {
        always {
	emailext body: 'helle day la jenkin nha', subject: 'test jenkin', to: 'datbeo12c@gmai.com'
        }
        success {
            echo 'I succeeded!'
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
        changed {
            echo 'Things were different before...'
        }
    }
}
