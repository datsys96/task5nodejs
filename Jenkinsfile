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
	emailext body: 'helle day la jenkin nha', subject: 'test jenkin', to: 'tuandatithubt@gmai.com'
        }
        success {
             mail to: 'tuandatithubt@gmail.com',
             subject: "success Pipeline: ${currentBuild.fullDisplayName}",
             body: "true  ${env.BUILD_URL}"
        }
        unstable {
             mail to: 'tuandatithubt@gmail.com',
             subject: "unstable Pipeline: ${currentBuild.fullDisplayName}",
             body: "unstable  ${env.BUILD_URL}"
        }
        failure {
             mail to: 'tuandatithubt@gmail.com',
             subject: "failure Pipeline: ${currentBuild.fullDisplayName}",
             body: "failse  ${env.BUILD_URL}"
        }
        changed {
             mail to: 'tuandatithubt@gmail.com',
             subject: "change Pipeline: ${currentBuild.fullDisplayName}",
             body: "change  ${env.BUILD_URL}"
        }
    }
}
