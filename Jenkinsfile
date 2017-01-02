#!/usr/bin/env groovy
def config ;
node {
    stage ("update config") {
        config = updateConfig({
            update = 'micro';
        });
    }
    stage ("get clean source") {
        getCleanGitSource(config);
    }
    stage("tag") {
        def ver = "frisotest";
        sh "git remote -v"
        sh "git  remote set-url origin ssh://${config['giturl']}"
        sh "git remote -v"
        sh "git tag -a '${ver}' -m 'Release tag by Jenkins'"
        sshagent([config['credid']]) { 
            sh "git -c core.askpass=true push origin '${ver}'"  
        }
    }
}
