pipeline {
    agent any
    stages {       
        stage('git') {
              steps {
                git branch: 'main', url: 'https://github.com/Srikanth0k/demo-new.git'
            }
        }
         stage('deploy on Remote Server (http://54.197.77.96)') {
            steps {
                sshPublisher(publishers: [sshPublisherDesc(configName: 'linux-slave-1008', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/var/www/html/', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/**')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
       
         stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
