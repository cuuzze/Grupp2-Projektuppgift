pipeline {
    environment {
            PATH = "C:\\WINDOWS\\SYSTEM32;C:\\Program Files\\Java\\jdk-17.0.1\\bin"

    }
    agent { label 'grupp2_jmeter' }
    
    stages{
        stage('Run Jmeter tests') {
            steps {

             bat 'C:\\tools\\apache-jmeter-5.4.1\\apache-jmeter-5.4.1\\bin\\jmeter.bat -Jjmeter.save.saveservice.output_format=xml -n -t C:\\tools\\apache-jmeter-5.4.1\\apache-jmeter-5.4.1\\bin\\PrestaShopReq4.jmx -l jmeter_report.jtl'
                perfReport 'jmeter_report.jtl'
	
	     bat 'C:\\tools\\apache-jmeter-5.4.1\\apache-jmeter-5.4.1\\bin\\jmeter.bat -Jjmeter.save.saveservice.output_format=xml -n -t C:\\tools\\apache-jmeter-5.4.1\\apache-jmeter-5.4.1\\bin\\PrestaShopReq5.jmx -l jmeter_report.jtl'
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