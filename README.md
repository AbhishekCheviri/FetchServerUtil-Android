# FetchServerUtil-Android
Android library for easily fetch data from server.
Add it in your root build.gradle at the end of repositories:

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

Initialise FetchServer

    FetchServer fetchServer = new FetchServer(this);
    
Set url of php or html file that you want to load.

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
