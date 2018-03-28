# MultiThreadDownload
Android Multi-Thread Download library.

###Demo
[Download](https://raw.githubusercontent.com/Aspsine/MultiThreadDownload/master/art/demo.apk)

###Demo ScreenShot
![Demo](https://github.com/Aspsine/MultiThreadDownload/raw/master/art/pic1.png)

###How to use
- Step 1: Add "compile project(':library')" in your 'build.gradle' file.(Maven or jCenter support will be coming soon)
- Step 2: Config it in your Application class
```Java
private void initDownloader() {
    DownloadConfiguration configuration = new DownloadConfiguration(getApplicationContext());
    // default download dir
    configuration.setDownloadDir(FileUtils.getDefaultDownloadDir(getApplicationContext()));
    // max thread number
    configuration.setMaxThreadNum(10);
    DownloadManager.getInstance().init(configuration);
}
```
- Step 3: Just use it!
```Java
// download
// the paramater dir here is a specical dir for this download
// if set null it will use default dir you have configed in Step 2;
DownloadManager.getInstance().download(appInfo.getName(), appInfo.getUrl(), dir, new CallBack() {

    @Override
    public void onDownloadStart() {
    
    }

    @Override
    public void onConnected(int total, boolean isRangeSupport) {
    
    }

    @Override
    public void onProgress(int finished, int total, int progress) {
    
    }

    @Override
    public void onComplete() {
    
    }

    @Override
    public void onDownloadPause() {
    
    }

    @Override
    public void onDownloadCancel() {
    
    }

    @Override
    public void onFailure(DownloadException e) {
    
    }
});

//pause
DownloadManager.getInstance().pause(appInfo.getUrl());

//cancel
DownloadManager.getInstance().cancel(appInfo.getUrl());

```

### Thanks
- link: http://www.imooc.com/learn/363
- Google Volley.

### Contact Me
- Github:   github.com/aspsine
- Email:    littleximail@gmail.com
- Linkedin: cn.linkedin.com/in/aspsine

### License

    Copyright 2015 Aspsine. All rights reserved.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
