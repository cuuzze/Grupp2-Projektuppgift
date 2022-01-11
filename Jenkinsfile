pipeline {
    environment {
            PATH = "C:\\Program Files\\Java\\jdk-17.0.1"
    }
    agent {   label 'grupp2_jmeter'   }
   
    stages{
        stage('Run Jmeter tests') {
            steps {
                 bat '${JMETER_HOME}\\jmeter.bat -Jjmeter.save.saveservice.output_format=xml -n -t ${JMETER_HOME}\\PrestaShopReq1.jmx -l jmeter_report.jtl'
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