pipeline {
    agent {
        label "jenkins-worker1"
    }

    stages {
        stage('Dotnet Verification') {
            steps {
                sh "dotnet --version"
            }
        }
        
        stage('Compile Application') {
            steps {
                sh "dotnet publish --self-contained -r linux-x64 -c Release"
            }
        }
        
        stage('Deploy Application') {
            steps {
                sh "rm -rf /tmp/proyecto-compilado/*"
                sh "cp -rf /tmp/workspace/primer-proyecto-romell/bin/Release/net5.0/linux-x64/publish/* /tmp/proyecto-compilado/"
                sh "cp lanzar_aplicacion.sh /tmp/proyecto-compilado/"
                sh "chmod +x lanzar_aplicacion.sh"
                sh "./lanzar_aplicacion.sh"
            }
        }
    }
}
