pipeline {
    environment {
            PATH = "C:\\WINDOWS\\SYSTEM32;C:\\Tools\\Java\\jdk-15.0.2\
                   "C:\\Program Files\\Java\\jdk-17.0.1\\bin"

    }
    agent any{ label 'grupp2_jmeter' }
    
    stages{
        stage('Run Jmeter tests') {
            steps {

                  
             bat 'C:\\tools\\apache-jmeter-5.4.1\\apache-jmeter-5.4.1\\bin\\jmeter.bat -Jjmeter.save.saveservice.output_format=xml -n -t C:\\tools\\apache-jmeter-5.4.1\\apache-jmeter-5.4.1\\bin\\Project_PrestaShop.jmx -l jmeter_report.jtl'
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