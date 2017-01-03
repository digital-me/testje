#!/usr/bin/env groovy
def config ;
node {
    stage ("update config") {
        config = updateConfig({
            update = 'micro';
            branch = 'TESTERDETEST';
            newVersion = 'versie';
        });
    }
    stage ("get clean source") {
        getCleanGitSource(config);
    }
    stage("tag") {
        tagGit(config);
    }
}
