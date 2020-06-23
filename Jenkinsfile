#!groovy

node {
    stage("checkout") {
        git url: "https://github.com/ramvalleru/JenkinsCIScan.git/", branch: "master", changelog: true, poll: false
        sh "pwd"
        sh "git diff --dirstat=files,0 HEAD~1"
    } 
}