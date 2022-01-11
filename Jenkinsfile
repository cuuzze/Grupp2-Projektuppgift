pipeline {
    environment {
            PATH = "C:\\Program Files\\Java\\jdk-17.0.1"
    }
    agent {   label 'Grupp2'   }
   
    stages{
        stage('Run Jmeter tests') {
            steps {
                 bat 'C:\\tools\\apache-jmeter-5.4.1\\bin\\jmeter.bat -Jjmeter.save.saveservice.output_format=xml -n -t C:\\tools\\apache-jmeter-5.4.1\\bin\\PrestaShopReq1.jmx -l jmeter_report.jtl'
                perfReport 'jmeter_report.jtl'
            }
        }
    }
   post {
        success {
            junit 'target/surefire-reports/**/*.xml'                       
        }
    }
}