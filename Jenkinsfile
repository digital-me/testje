#!/usr/bin/env groovy
def config ;

stage ("update config") {
    config = updateConfig({
        update = 'micro';
    }):
}
stage("tag") {
    def ver = "frisotest";
    sh "git tag -a '${ver}' -m 'Release tag by Jenkins'"
    sshagent([config['credid']]) { 
        sh "git -c core.askpass=true push origin '${ver}'"  
    }
}
