#!groovy

node {
    git url: "https://github.com/ramvalleru/JenkinsCIScan.git/", branch: "master", changelog: true, poll: false
    sh "git diff --dirstat=files,0 HEAD~1 | sed -E \'s/^[ 0-9.]+% //g\'"
}