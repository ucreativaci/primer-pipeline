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
                sh "rm -rf /tmp/workspace/primer-proyecto-romell/bin/Release/net5.0/linux-x64/publish/*"
                sh "dotnet publish --self-contained -r linux-x64 -c Release"
            }
        }
        
        stage('Deploy Application') {
            steps {
                sh "rm -rf /tmp/proyecto-compilado/*"
                sh "cp -rf /tmp/workspace/primer-proyecto-romell/bin/Release/net5.0/linux-x64/publish/* /tmp/proyecto-compilado/"
                sh "/tmp/proyecto-compilado/lanzar_aplicacion.sh"
            }
        }
    }
}
