#!groovy

@NonCPS
def folderstofeatures(folders) {
    def changedFeatures = []
    folders.each { String line ->
        changedFeatures.add(line.trim())
    }
    return changedFeatures
}

def nodenames() {
    return jenkins.model.Jenkins.instance.nodes.collect { node -> node.name }
}

node {
    stage("checkout") {
        git url: "https://github.com/ramvalleru/JenkinsCIScan.git/", branch: "master", changelog: true, poll: false
        
        // Retrieves changed feature folders
        def changedFolders = sh(script: "git diff --dirstat=files,0 HEAD~1 | sed -E 's/^[ 0-9.]+% //g'", returnStdout: true).split('\n')
        def wrkDir = sh(script: "pwd", returnStdout: true).trim()
        
        // adds absolute patch of the changed feature directory
        def changedFeatures = folderstofeatures(changedFolders).collect { folder ->
            return wrkDir+"/"+folder
        }
        changedFeatures.each { String folder ->
            println(folder)
        }

        def branches = [:]
        def node_names = nodenames()
        println(node_names)
        
        
    } 
}

