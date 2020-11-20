pipeline {
  stages {
  	stage('Checkout') {
      steps {
        git credentialsId: 'f73333eb-8b72-4e42-b0c6-363a9e60e830', url: 'git@github.com:PartTimeLegend/lfs.git', branch: 'master'
      }
    }
    stage('Install'){
      steps{
        bat "git lfs install"
      }
    }
    stage('Migrate'){
      steps{
        bat "git lfs migrate import --everything --yes --verbose"
      }
    }
    stage('Push changes'){
      steps{
        bat "git push origin --all --progress --porcelain --thin"
      }
    }
  }    
}
