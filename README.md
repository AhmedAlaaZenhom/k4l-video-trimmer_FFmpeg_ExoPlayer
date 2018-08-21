

### This project is the re-implementation of k4l-video-trimmer video trimming library(using the same UI) with FFmpeg(instead of IsoPasrer) & ExoPlayer(instead of videoView & mediaplayer)

### This re-implementation fixes the trimming time interval accuracy issues caused by videos with discrete & Spaced out sync frames

# VideoTrimmer: https://github.com/titansgroup/k4l-video-trimmer
# FFmpeg: https://github.com/bravobit/FFmpeg-Android
# ExoPlayer: https://developer.android.com/guide/topics/media/exoplayer

#### This project aims to provide an ultimate and flexible video trimmer experience.

<img src="https://raw.githubusercontent.com/knowledge4life/k4l-video-trimmer/master/screenshot/screenshot.png" alt="VideoTrimmer Screenshot" width="360" height="640" />

## [Watch a DEMO here](http://gfycat.com/UnnaturalConsiderateFiddlercrab)

# Usage

*For a working implementation, please have a look at the Sample Project - sample*

1. Import the library as a module and perform your changes on it if you want
    
2. Add K4LVideoTrimmer component into your layout.

    ```
    <life.knowledge4.videotrimmer.K4LVideoTrimmer
        android:id="@+id/timeLine"
        android:layout_height="match_parent"
        android:layout_width="match_parent" />
    ```

3. Set the K4LVideoTrimmer selected video Uri.

    ```java
    K4LVideoTrimmer videoTrimmer = ((K4LVideoTrimmer) findViewById(R.id.timeLine));
    if (videoTrimmer != null) {
        videoTrimmer.setVideoURI(Uri.parse(path));
    }
    ```

# Default destination folder
    Environment.getExternalStorageDirectory()

# Here is an example of a listener implementation.

1. Implements `OnTrimVideoListener` methods

    ```java
    @Override
    public void getResult(final Uri uri) {
        // handle K4LVideoTrimmer result.
    }

    @Override
    public void cancelAction() {
        // handle K4LVideoTrimmer cancel action
    }
    ```

# Customization

* Custom destination folder
    ```java
    videoTrimmer.setDestinationPath("/storage/emulated/0/DCIM/CameraCustom/");
    ```

* Set maximum video time interval
    ```java
    videoTrimmer.setMaxDuration(10);
    ```


# Known issues and limitations
- Thumbnails are only added to the timeline once all of them are created in a background thread
- We only support MP4 files
- Methods count: 5768 from Isoparser + 237 from K4l-video-trimmer
    
# Compatibility
  
  * Library - Android ICS 4.1+ (API 21)
  * Sample - Android ICS 4.1+ (API 21)
  
  ```
