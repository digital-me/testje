#!/usr/bin/env groovy
     
def config=[release: false];
    
try {
     config['release'] = Boolean.valueOf(release);
     println release.getClass()
     if (release) {
         println "release $release";
     } else {
         println "not a release";
     }
} catch (MissingPropertyException e) {
     config['release'] = false;
}


println "release = ${config['release']}"
