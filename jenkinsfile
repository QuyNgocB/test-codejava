pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Bước 1: Biên dịch chương trình Java và di chuyển tệp .class vào thư mục output
                sh 'javac -d output HelloWorld.java'
            }
        }
        stage('Run') {
            steps {
                // Bước 2: Chạy chương trình Java từ tệp .class
                sh 'java -cp output HelloWorld'
            }
        }
    }
}
