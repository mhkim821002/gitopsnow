pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/mhkim821002/gitopsnow.git will replace by sed command before RUN
        git url: 'https://github.com/mhkim821002/gitopsnow.git', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}