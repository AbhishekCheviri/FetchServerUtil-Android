# FetchServerUtil-Android
An Android library that simplifies Requesting and Fetching of data from the server.
Add below code to the root build.gradle at the end of repositories:

    allprojects {
		    repositories {
			    ...
			    maven { url 'https://jitpack.io' }
		    }
	  }
    
Add the dependency
    
    dependencies {
	        compile 'com.github.Abhishekpalodath:FetchServerUtil-Android:0.1.2'
	  }

Initialize fetch server

    FetchServer fetchServer = new FetchServer(this);
    
Load the desired php/html code using setUrl method.

    fetchServer.setUrl("https://something.php");

Add onPreExecute listener for pre execution of data and onPostExecute listener fetches out the loaded data from the url
    
    fetchServer.setOnFetchListener(new FetchServer.OnFetchListener() {
            @Override
            public void onPreExecute() {
                ...
            }

            @Override
            public void onPostExecute(String result) {
                ...
            }
        });
  
execute() loads the given url.

    fetchServer.execute();
    
You can set data to be posted into the php file by using-

    fetchServer.setPostDataParams("key","value");
    
Also you can load real-time data from the server.

    fetchServer.setLoadRealtime(true);
