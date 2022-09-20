pipeline {
     
     
     
     agent any
     
     
     tools {nodejs "my-node"}
   
    
     
     
     stages {
        stage("Build") {
            steps {
                sh "npm install"
                sh " npm run build"
            }
        }
        stage("Deploy") {
            steps {
              
         sshPublisher(publishers: [sshPublisherDesc(configName: 'react server', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: 'react-pipeline', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'build')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
    }
}
