pipeline{

      agent any
        
        stages{

              stage('sonarqube env setup') {
                  steps{

                    sh '''export SONAR_SCANNER_VERSION=4.7.0.2747
                     export SONAR_SCANNER_HOME=$HOME/.sonar/sonar-scanner-$SONAR_SCANNER_VERSION-linux
                     curl --create-dirs -sSLo $HOME/.sonar/sonar-scanner.zip https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-$SONAR_SCANNER_VERSION-linux.zip
                     unzip -o $HOME/.sonar/sonar-scanner.zip -d $HOME/.sonar/
                     export PATH=$SONAR_SCANNER_HOME/bin:$PATH
                     export SONAR_SCANNER_OPTS="-server"

                     sonar-scanner \\
                     -Dsonar.projectKey=test \\
                     -Dsonar.sources=. \\
                     -Dsonar.host.url=http://54.203.27.50:9000 \\
                     -Dsonar.login=sqp_e3154bbad23001b9b2569b22c2ad78ecaea99945

                    '''
                  }
              }   
              //stage('Quality Gate Status Check'){
              //    steps{

              //      sh '''
              //       sonar-scanner \\
              //       -Dsonar.projectKey=test \\
              //       -Dsonar.sources=. \\
              //       -Dsonar.host.url=http://54.203.27.50:9000 \\
              //       -Dsonar.login=sqp_e3154bbad23001b9b2569b22c2ad78ecaea99945

               //     '''

                //  }
             // }
              
  
		    	    
		  
                 	}
               	 }
                
            	
		
            	       	     	
