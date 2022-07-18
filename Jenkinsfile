pipeline {
    agent any
    stages {
        stage('---install apache---') {
            steps {
                sh "sudo apt install apache2 -y"
                sh "sudo systemctl status apache2"
            }
        }
        stage('---install some tools---') {
            steps {
                sh "sudo apt install wget zip unzip -y"
            }
        }
        stage('--download source webfile--') {
            steps {
                sh "sudo wget https://www.free-css.com/assets/files/free-css-templates/download/page280/spa-center.zip"
                sh "sudo unzip ./spa-center.zip  && sudo cp -rf spa-html-template/* /var/www/html/"
                //sh "sudo mv /var/www/html/spa-html-template/* /var/www/html/"
                //sh "sudo rm -rf /var/www/html/spa-html-template /var/www/html/spa-center.zip"
            }
        }
        stage('--restart the apache2 server--') {
            steps {
                sh "sudo systemctl restart apache2"
            }
        }
    }
}