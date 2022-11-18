pipeline{
  agent any 

  stages{
    stage(checkout){
       steps{
    checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/dinu2907/my-tf-iac-aws-repo.git']]])
     }
   }
    
   stage(Iniatikizaing & Formatting){
       steps{
    sh('terraform init')
    sh('terraform fmt')
     }
   }
    
    
    
    
  }
}
