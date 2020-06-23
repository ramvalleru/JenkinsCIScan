#!groovy

stage('setupenv') {
  node label: "node1",  body: {
      sh 'mkdir -p ' + builddir
    dir(builddir) {
      checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'SubmoduleOption', disableSubmodules: false, parentCredentials: false, recursiveSubmodules: true, reference: '', trackingSubmodules: false]], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/ianmiell/shutit']]])
    }
  }
  
}