pipeline {
    parameters {
        string(name: 'name', defaultValue: 'akbar', description: 'enter your name')
    }
    environment {
        df_path = "${workspace}"
    }
    agent any
    stages {
        stage('checkout') {           
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'raji_git', url: 'https://github.com/rajeeb007/test1.git']]])  
            }
        }
        stage('Update Version') {
            steps {
                script {
                    sh """
                    echo "hi rajeeb, this is inside of readme text file"
                    cat $df_path/README.md
                    echo "this project is done by ${params.name}"
                    """
                }
            }
        }   
    }  
  }
