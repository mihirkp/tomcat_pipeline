pipeline {
   agent any

   tools {
      // Install the Maven version configured as "M3" and add it to the path. Demo comment
      maven "maven"
      jdk "java"
                
   }

   stages {
      stage('Code Checkout') {
         steps {
            // Get some code from a GitHub repository
            git 'https://github.com/mihirkp/tomcat_pipeline.git'   
         }

      }
      
      stage(' Code Testing') {
         steps {
           
            bat "mvn test"
         }

      }
      
       stage(' Code Compilation') {
         steps {
           
            bat "mvn compile"
         }

      }
      
      stage(' Code Build') {
         steps {
           
            // To run Maven on a Windows agent, use
           bat "mvn package"
         }

      }
      
      stage('Code Deploy') {
         steps {
        
            // To run Maven on a Windows agent, use
           bat label: '', script: 'copy /Y target\\tomcat-1.0.war C:\\Users\\mihir\\Downloads\\apache-tomcat-9.0.37\\webapps'
         }

      }
   }
}
