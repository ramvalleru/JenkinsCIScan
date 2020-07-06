#!groovy

node {
    stage("checkout") {
        git url: "https://github.com/ramvalleru/JenkinsCIScan.git/", branch: "master", changelog: true, poll: false
        
        // Retrieves changed feature folders
        def changedFeatures = sh(script: "git diff --dirstat=files,0 HEAD~1 | sed -E 's/^[ 0-9.]+% //g' | cut -d '/' -f-2", returnStdout: true).split('\n')//.collect { if (it != '') return it}

        println changedFeatures instanceof String[]
        println changedFeatures.length
        println changedFeatures[0]
      
        if(changedFeatures.length == 1 && changedFeatures[0] == null) {
            println "nothing to run"
        } else {
            changedFeatures.each { feature_folder ->
            println "feature_folder ${feature_folder}"
            /*build job: 'tibcojob', parameters: [
                string(name: 'featureFolder', value: feature_folder)
            ]*/
        }
        }

        
     
    } 
}

