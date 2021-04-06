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
	emailext body: 'helle day la jenkin nha', subject: 'test jenkin', to: 'datbeo12c@gmail.com'
        }
	        success {
            emailext body: 'ok', subject: '${DEFAULT_CONTENT}', to: '${DEFAULT_SUBJECT}'
        }
        unstable {
            emailext body: 'unstable', subject: '${DEFAULT_CONTENT}', to: '${DEFAULT_SUBJECT}'
        }
        failure {
            emailext body: 'failure', subject: '${DEFAULT_CONTENT}', to: '${DEFAULT_SUBJECT}'
        }
        changed {
            emailext body: 'change', subject: '${DEFAULT_CONTENT}', to: '${DEFAULT_SUBJECT}'
        }
    }
}
