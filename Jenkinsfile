pipeline {
    agent {
        kubernetes {
            label 'my-kubernetes-agent' // Thay 'my-kubernetes-agent' bằng label Kubernetes của bạn
        }
    }
    
    stages {
        stage('Clone repository') {
            steps {
                // Bước checkout mã nguồn từ repository
                git 'https://github.com/QuyNgocB/test-codejava.git'
            }
        }
        
        stage('Build and push Docker image') {
            steps {
                // Bước biên dịch mã nguồn và đẩy hình ảnh Docker lên Docker Hub
                script {
                    sh 'docker build -t bnquy/ngocquy123:latest .'
                    sh 'docker push bnquy/ngocquy123:latest'
                }
            }
        }
        
        stage('Deploy to Kubernetes') {
            steps {
                // Triển khai ứng dụng lên Kubernetes
                kubernetesDeploy(
                    configs: 'kubernetes/deployment.yaml',
                    kubeconfigId: 'my-kubeconfig'
                )
            }
        }
    }
}
