pipeline {
    agent any

    environment {
        HTTPD_VERSION = "2.4"  // вкажіть версію Apache2
    }

    stages {
        stage('Install Apache2') {
            steps {
                script {
                    // Перевірка наявності Apache2 та встановлення
                    sh '''
                    sudo apt update
                    sudo apt install -y apache2
                    sudo systemctl enable apache2
                    sudo systemctl start apache2
                    '''
                }
            }
        }

        stage('Verify Apache2 Installation') {
            steps {
                script {
                    // Перевірка чи працює Apache2
                    sh "systemctl status apache2"
                }
            }
        }
    }
}
