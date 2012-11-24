### Audjustable Audio Streamer

[Homepage](http://tumtumtum.github.com/audjustable)

Audjustable is audio streaming class for iOS and OSX.  Audjustable uses CoreAudio to decompress and playback audio whilst providing a clean and simple object-oriented API.

## Features

* Simple OOP API
* Easy to read source
* Adjustable audio buffering
* Buffered and gapless playback
* Easy to implement audio data sources (HTTP and local file system DataSources provided)
* Easy to extend DataSource to support adaptive buffering, encryption etc
* Optimised for low CPU/battery usage

## Usage

Download the [source](https://github.com/tumtumtum/audjustable/zipball/master) which includes a simple audio player project that streams audio over HTTP or locally using the `HttpDataSource` or `LocalFileDataSource` classes respectively.

If you would like to integrate the AudioPlayer directly into your project you only need to copy the files inside the `/Audjustable/Classes/AudioPlayer` [directory](https://github.com/tumtumtum/audjustable/tree/master/Audjustable/Classes/AudioPlayer) into your project.

## Code

There are two main classes.  The `DataSource` class which is the abstract base class for the various compressed audio data sources (HTTP, local file are provided). The `AudioPlayer` class manages and renders audio from a queue DataSources.

```objective-c

// Create AudioPlayer

AudioPlayer* audioPlayer = [[AudioPlayer alloc] init];
audioPlayer.delegate = self;

// Queue on a URL to play.  Each queue item has a unique ID (item1) that to identify the related file in delegate callbacks

[audioPlayer setDataSource:[audioPlayer dataSourceFromURL:@"https://github.com/downloads/tumtumtum/audjustable/sample.m4a"] withQueueItemId:@"item1"];

```

## Other

Background playback on iOS is easily added to your application by using the  `AudioSessionInitialize` to your AppDelegate.

### Authors and Contributors
Copyright 2012, Thong Nguyen (@tumtumtum)