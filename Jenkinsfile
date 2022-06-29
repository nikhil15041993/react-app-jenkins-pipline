pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                sh "sudo npm install"
                sh "sudo npm run build"
            }
        }
        stage("Deploy") {
            steps {
                sh "sudo rm -rf /home/react/react-app-pipeline/*"
                sshPublisher(publishers: [sshPublisherDesc(configName: 'react', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/home/react/react-app-pipeline', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'build/')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
                 
                
            }
        }
    }
}
