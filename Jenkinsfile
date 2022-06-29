pipeline {
     
     
     
     agent any
     
     
     tools {nodejs "Nodejs"}
   
    
     
     
     stages {
        stage("Build") {
            steps {
                sh "sudo npm install"
                sh "sudo npm run build"
            }
        }
        stage("Deploy") {
            steps {
                
                sshPublisher(publishers: [sshPublisherDesc(configName: 'react', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/home/react/react-app-pipeline', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'build/')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
                 
                
            }
        }
    }
}
