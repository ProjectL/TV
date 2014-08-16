##Project L

###LoQooTV
================

This class represents the Logic behind a typical L TV Channel.

In this Android Client the channel interface is mostly constructed with the use of Fragments.
Fragments are self contained "screens" that can contain a visual layout, as well as Logic.
A Fragment can exist within an activity and not been seen. As well as enter the Activity @ a later time.

The intial setup is of a Footer Fragment, is added to the Channel, this Fragment is being used to convey
instructions to the user on how to start subscribe/follow this channel.

Here's the code setting up the intial Fragments:
```java

        //SETUP INTIAL FRAGMENTS
        FragmentManager fragmentManager = getFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragMain fragMain = new FragMain();
        FragFooter fragFooter = new FragFooter();
        fragmentTransaction.add(R.id.pip_fragment, fragMain);
        fragmentTransaction.add(R.id.footer_fragment, fragMain);
        fragmentTransaction.commit();
```

Also, being setup in this Channel Activity is a BroadcastReceiver, an internal one which can only receive broadcast
when the Activity is in the forefront, meaning being shown.

Here's the code related to the Dynamic BroadcastReceiver that is structured as an Inner Class of the Activity:
```java
	@Override
	protected void onResume() {
		super.onResume();
		fullscreen();
		Log.d("LifeCycle.TV.onResume","onResume");
    	IntentFilter intentFilter = new IntentFilter();
        intentFilter.addAction("tv.loqoo.v4.ORIGINAL_VIDEO_SCENE");
        intentFilter.addAction("tv.loqoo.v4.ORIGINAL_AUDIO_SCENE");
        intentFilter.addAction("tv.loqoo.v4.ORIGINAL_IMAGE_SCENE");
        intentFilter.addAction("tv.loqoo.v4.ORIGINAL_COMMENT_SCENE");
        intentFilter.addAction("tv.loqoo.v4.ORIGINAL_MAP_SCENE");
        intentFilter.addAction("tv.loqoo.v4.ORIGINAL_WWW_SCENE");
    	registerReceiver(mloqooBroadcast, intentFilter);
		Log.d("LifeCycle.LTV.ONresume","register_receiever");
	}

public loqooBroadcast mloqooBroadcast = null;

	@Override
	protected void onPause()
	{
		super.onPause();
		Log.d("LifeCycle.TV.onPause","ONPause");
		unregisterReceiver(mloqooBroadcast);
	}
	
public class loqooBroadcast extends BroadcastReceiver{
	    @Override
	    public void onReceive(Context context, Intent intent) {
	    	Log.d("mloqooBroadcast","start_onRecieve_Insideactivity");
	    	Bundle argsVideo = new Bundle();
	    	Bundle argsAudio = new Bundle();
	    	Bundle argsImage = new Bundle();
	    	Bundle argsMeta = new Bundle();
	        if (intent.getAction().equals("tv.loqoo.v4.ORIGINAL_VIDEO_SCENE")) {
	        	Log.d("TV.channel001.videoScene", "starting videoScene");
	        	incomingScene(intent,message,argsVideo,argsMeta,fragVideo,"video");
	        }else if(intent.getAction().equals("tv.loqoo.v4.ORIGINAL_AUDIO_SCENE")){
	        	Log.d("TV.channel001.audioScene", "starting audioScene");
				incomingScene(intent,message,argsAudio,argsMeta,fragAudio,"audio");
	        }else if(intent.getAction().equals("tv.loqoo.v4.ORIGINAL_IMAGE_SCENE")){
	        	Log.d("TV.channel001.imageScene", "starting imageScene");
		        incomingScene(intent,message,argsImage,argsMeta,fragImage,"image");
	        }
	    }
	};

```

The BroadcastReceiver is waiting for an Incoming Scene which can be an audio, video, or textual message a subscriber
is publishing for display.

