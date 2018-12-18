pipeline {
   agent any
   tools {
         maven 'apache-maven-3.5.2'
         jdk 'jdk1.8.0_181'
   }
   stages {
   stage ('Build'){
      steps {
       bat 'mvn compiler:compile'
       bat 'mvn install'
         bat 'mvn site'
         bat 'mvn cobertura:cobertura'
       }
       post {
       success {
       junit 'target/surefire-reports/**/*.xml'
       cobertura coberturaReportFile: '**/target/site/cobertura/coverage.xml'
       }
       }
       }
       }
       }
      
   
