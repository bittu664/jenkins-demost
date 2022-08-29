pipeline{

      agent any
        
        stages{

              stage('Quality Gate Status Check'){
                  steps{
                      script{
			 export SONAR_SCANNER_VERSION=4.7.0.2747
                         export SONAR_SCANNER_HOME=$HOME/.sonar/sonar-scanner-$SONAR_SCANNER_VERSION-linux
                         curl --create-dirs -sSLo $HOME/.sonar/sonar-scanner.zip https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-$SONAR_SCANNER_VERSION-linux.zip
                         unzip -o $HOME/.sonar/sonar-scanner.zip -d $HOME/.sonar/
                         export PATH=$SONAR_SCANNER_HOME/bin:$PATH
                         export SONAR_SCANNER_OPTS="-server"
			 timeout(time: 1, unit: 'HOURS') {
			 def qg = waitForQualityGate()
				 if (qg.status != 'OK') {
				     error "Pipeline aborted due to quality gate failure: ${qg.status}"
				      }
                    		}
		    	    
		  
                 	}
               	 }  
              }	
		
            }	       	     	         
}
