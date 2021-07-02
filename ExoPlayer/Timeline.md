### Timeline

https://exoplayer.dev/doc/reference/com/google/android/exoplayer2/Timeline.html

Timeline是对媒体描述文件的抽象。

A flexible representation of the structure of media. 用于表示媒体结构。比如DashTimeline。

A timeline consists of [`Windows`](https://exoplayer.dev/doc/reference/com/google/android/exoplayer2/Timeline.Window.html) and [`Periods`](https://exoplayer.dev/doc/reference/com/google/android/exoplayer2/Timeline.Period.html).

- A [`Timeline.Window`](https://exoplayer.dev/doc/reference/com/google/android/exoplayer2/Timeline.Window.html) 资源列表

  usually corresponds to one playlist item. It may span one or more periods and it defines the region within those periods that's currently available for playback. The window also provides additional information such as whether seeking is supported within the window and the default position, which is the position from which playback will start when the player starts playing the window.

- A [`Timeline.Period`](https://exoplayer.dev/doc/reference/com/google/android/exoplayer2/Timeline.Period.html) 单个的媒体片段

  defines a single logical piece of media, for example a media file. It may also define groups of ads inserted into the media, along with information about whether those ads have been loaded and played.

#### Period

https://exoplayer.dev/doc/reference/com/google/android/exoplayer2/Timeline.Period.html

#### Window

https://exoplayer.dev/doc/reference/com/google/android/exoplayer2/Timeline.Window.html