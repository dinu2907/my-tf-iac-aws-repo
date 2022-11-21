pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
            checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/dinu2907/my-tf-iac-aws-repo.git']]])          

          }
        }
        
        stage ("terraform init & Fmt") {
            steps {
                sh ('terraform init') 
                sh ('terraform fmt') 
            }
        }
        
        
        stage('Check Terraform configurations with tflint'){
                    steps {
                        // To install tflint
                        // curl -L -o /tmp/tflint.zip https://github.com/wata727/tflint/releases/download/v0.4.2/tflint_linux_amd64.zip && unzip /tmp/tflint.zip -d /usr/local/bin
                        sh  "tflint"
                    }
                }
        
        stage ("terraform Action") {
            steps {
                echo "Terraform action is --> ${action}"
                sh ('terraform ${action} --auto-approve') 
           }
        }
        
       
        
        
    }
}
