# FetchServerUtil-Android
Android library that fetches data from the server.
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

You can add onPreExecute and onPostExecute listeners.

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
  
Start loading using the code

    fetchServer.execute();
    
You can set data to be posted into the php file by using-

    fetchServer.setPostDataParams("key","value");
    
Also you can load realtime data from server by using

    fetchServer.setLoadRealtime(true);
    
Which is actually continues fetching of given url.
