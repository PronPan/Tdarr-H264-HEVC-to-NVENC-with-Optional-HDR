# Tdarr-H264-HEVC-to-NVENC-with-Optional-HDR

This  plugin will transcode H264 or reconvert HEVC files using NVENC with bframes, 10bit, and (optional) HDR. Requires a Turing NVIDIA GPU or newer.  
  
If reconvert HEVC is on and the entire file is over the bitrate filter, the HEVC stream will be re-encoded. Typically results in a 50-75% smaller size with little to no quality loss.

When setting the re-encode bitrate filter be aware that it is a file total bitrate, so leave overhead for audio.

Because of the heavily tweaked ffmpeg encoder settings, HEVC->HEVC reconverting usually results in a higher bitrate than the target bitrate.

This plugin implements the filter_by_stream_tag plugin to prevent infinite loops caused by that higher bitrate being above target bitrate.

By default, all settings are ideal for most use cases

Example screenshots:

![Screenshot 2023-12-31 152131](https://github.com/PronPan/Tdarr-H264-HEVC-to-NVENC-with-Optional-HDR/assets/5284391/619f1b39-b814-4b1f-b8c7-2ae07416d5a7)

![Screenshot 2023-12-31 152201](https://github.com/PronPan/Tdarr-H264-HEVC-to-NVENC-with-Optional-HDR/assets/5284391/ddabcd0a-ffc6-43a5-898a-cdbcb3dd665c)

![Screenshot 2023-12-31 152216](https://github.com/PronPan/Tdarr-H264-HEVC-to-NVENC-with-Optional-HDR/assets/5284391/5a201de8-b878-439b-b229-f5b5d257ea2c)
