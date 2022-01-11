pipeline {
    environment {
            PATH = "C:\\Program Files\\Java\\jdk-17.0.1"
    }
    agent {   label 'Grupp2JMeter'   }
   
    stages{
        stage('Run Jmeter tests') {
            steps {
                bat "${JMETER_HOME}\\bin\\jmeter.bat -Jjmeter.save.saveservice.output_format=xml -n -t ${JMETER_HOME}\\bin\\PrestaShopReq1.jmx -l jmeter_report.jtl"
                perfReport 'jmeter_report.jtl'
            }
        }
    }
    post {
        success {
            junit allowEmptyResults: true, testResults: "${WORKSPACE}/test-results/*.xml"                       
        }
    }
}