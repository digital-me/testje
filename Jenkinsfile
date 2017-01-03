#!/usr/bin/env groovy
def config ;
node {
    stage ("update config") {
        config = updateConfig({
            update = 'micro';
            branch = 'master';
            newVersion = '0.0.1';
        });
    }
    stage ("get clean source") {
        getCleanGitSource(config);
    }
    stage("tag") {
        tagGit(config);
    }
}
