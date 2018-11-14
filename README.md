# androidwave-master
修改了原github上androidwave-master工程代码，在文件：
androidwave-master\src\org\yuttadhammo\androidwave.java中修改如下：

1、将原先MediaPlayer的创建方法：
mp = MediaPlayer.create(AndroidWave.this,Uri.fromFile(playingFile));
改为 mp = new MediaPlayer(); 

2、增加了对setAudioStreamType类型的设置，可以支持对两种音频流的测试：

//mp.setAudioStreamType(AudioManager.STREAM_VOICE_CALL);
		mp.setAudioStreamType(AudioManager.STREAM_MUSIC);
		try {
			mp.setDataSource(getApplicationContext(), Uri.fromFile(playingFile));
			mp.prepare();
		} catch (IllegalArgumentException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		} catch (SecurityException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		} catch (IllegalStateException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		} catch (IOException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
