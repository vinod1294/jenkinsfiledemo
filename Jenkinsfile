node()
{
    try
		{
		String str = "devejjlop"
    	stage 'Select Build type1'
    	
    	//Feature branch added
	    if ("${env.JOB_NAME}" == 'pileline-abdul') 
			{
			 print "Building the abdul branch "
			/***Calling the function developBranch if develop branch is being built***/
			 developBranch()
			}
			else if ( str == 'master') 
			{
			 print "Building the master branch "
			/***Calling the function masterBranch if master branch is being built***/
			 masterBranch()
			}
	    else  
			{
			 print "Building the feature branch"
			/***Calling the function featureBranch if feature branch is being built***/
			 featureBranch()
			}
		} 
	catch(e) 
		{
		currentBuild.result = "FAILED"	
		//notifyBuild(currentBuild.result)
		throw(e)
		} 
    finally 
		{
		echo "echo final block"
		}	
	}
	
	
	
def developBranch() 
	{
	
/***Download code from stash***/  
    stage ("Download code")
    {
		download_stash_code()
    }
	
	/***Perform maven clean***/ 	        
    stage ("Clean")
    {
		clean()
    }
	/***Perform maven mUnit tests***/    	
	stage ("mUnit Tests")
	{
		//munit_tests()
	}
	/***Publish the coverage report and junit reports***/  
	stage ("Publish Reports")
	{
		publish_junit()
		publish_html()
	}
	/***Create zip package from the source code and push it to artifactory***/		  
    stage ("Package & Publish")
    {
		package_publish_artifactory()
   }
}

def masterBranch() 
	{
	
	print "inside masterBranch() "
	/***Download code from stash***/  
	stage ("Download Code")
	{
		download_stash_code()
	}
	/***Perform maven clean***/ 	    
	stage ("Clean")
		clean()
	
	/***Perform maven mUnit tests***/ 		
	stage ("mUnit Tests"){
	   	//munit_tests() 
	}
	
	
	/***Publish the coverage report and junit reports***/		
	stage ("Publish Reports"){
		publish_junit()
		publish_html()
	}
	/***Create zip package from the source code and push it to artifactory***/
  	stage ("Package & Publish"){
  	    package_publish_artifactory_master()
  	}
	
	}
def featureBranch() 
	{
	
	/***Download code from stash***/  
    stage ('Download Code'){
    
		download_stash_code()
    }
	/***Perform maven clean***/ 
    stage (" Clean")
    {
		clean()
    }
	
	/***Perform maven mUnit tests***/     	
	stage ("mUnit Tests"){
		//munit_tests()
	}	
	/***SoapUI Integration Tests***/ 
	stage ("SoupUI Integration Testing")
	{
		download_soapUi_code()
	}
	
	/***Publish the coverage report and junit reports***/			
	stage ("Publish Reports"){
		publish_junit()
		publish_html()
	}
	/***Create zip package from the source code and push it to artifactory***/
	stage ("Package & Publish")
	{
		package_publish_artifactory_master()
	    
	}
		
	}


/***Function definitions start from here***/ 	

	/***Function definition for downloading code from Stash to workspace in jenkins***/ 	
	def download_stash_code()
	{
	print "inside download_stash_code() "
	}		
	
	/***Function definition to perform maven clean***/ 
	def clean()
	{
	print "inside clean() "
	}
	def publish_junit()
	{
	print "inside publish_junit()"
	}
	def publish_html()
	{  
 	print "inside publish_html()"
		
	}	
	
	/***Function definition to push the artifacts to artifactory***/   
	def package_publish_artifactory()
	{
	    print "inside package_publish_artifactory()"
	}
   
   /***Download SoapUI Scripts from the Stash and executing them***/
	def download_soapUi_code()
	{
        print "download_soapUi_code()"
    }
    
    /***Function definition to push the artifacts to artifactory for the master branch, performs maven release***/ 
	def package_publish_artifactory_master()
	    
	{
		print "inside  package_publish_artifactory_master()"
	}
