# flutter_app_youtbue_player

A new Flutter application.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://flutter.dev/docs/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://flutter.dev/docs/cookbook)

For help getting started with Flutter, view our
[online documentation](https://flutter.dev/docs), which offers tutorials,
samples, guidance on mobile development, and a full API reference.
# Flutter-YoutubePlayerSample

youtube_player_flutter: ^7.0.0+7
https://pub.dev/packages/youtube_player_flutter

支援平台:

Android

iOS

Requirements #

Android: 最小 minSdkVersion 17 並且支援 androidx (see AndroidX Migration) 並且需要API 20以上

iOS: --ios-language swift, Xcode 版本需要 >= 11

在pubspec.yaml 加入
        
               dependencies:
                   youtube_player_flutter: ^7.0.0+7


加入完後 記得下指令 安裝
        
                $ flutter pub get
                
使用youtube player

                //設定初始控制元件
                YoutubePlayerController _controller = YoutubePlayerController(
                    initialVideoId: 'iLnmTe5Q2Qw',//要播放的youtube video id
                    flags: YoutubePlayerFlags(
                        autoPlay: true, //是否自動播放
                        mute: true,//是否靜音
                    ),
                );

                YoutubePlayer(
                    controller: _controller,
                    showVideoProgressIndicator: true,
                    videoProgressIndicatorColor: Colors.amber,
                    progressColors: ProgressColors(
                        playedColor: Colors.amber,
                        handleColor: Colors.amberAccent,
                    ),
                    onReady () {
                        _controller.addListener(listener);
                    },
                ),
                
播放直播影片 (其實沒有設定成這樣好像也可以播放，但直播的操作介面跟影片的不同！如果不介意就沒差！)
        
        YoutubePlayerController _controller = YoutubePlayerController(
            initialVideoId: 'iLnmTe5Q2Qw',
            flags: YoutubePLayerFlags(
              isLive: true,
            ),
        );

        YoutubePlayer(
            controller: _controller,
            liveUIColor: Colors.amber,
        ),
