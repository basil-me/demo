pipeline {
    agent any
    stages {
         stage('Remote login') {
             steps {
                 script {
                         def remote = [:]
                         remote.name = "reactapp-store"
                         remote.host = "10.0.0.158"
                         remote.port = 22
                         remote.allowAnyHosts = true
                         withCredentials([sshUserPrivateKey(credentialsId: 'reactapp-store', keyFileVariable: 'reactapp-store', usernameVariable: 'ubuntu')]){
                                 remote.user = ubuntu
                                 remote.identityFile = reactapp-store
                                 stage("Git clone and Rsync") {
                                     sshCommand remote: remote, command: 'sudo https://github.com/basil-me/demo.git'
                                     sshCommand remote: remote, command:  date
                                 }
                                                              
                           }
                    }
            }
         }
     }
}
