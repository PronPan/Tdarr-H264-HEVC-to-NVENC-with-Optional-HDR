#purpan's H264/HEVC to NVENC with Optional HDR

Plugin utilizes code from multiple others such as the generic sort_by_stream_tag plugin, but mostly [tws101's Ultimate_GPU_Transcoder_HDR](https://github.com/HaveAGitGat/Tdarr_Plugins/blob/4e0dd002c249247d338bf52c0595df917532eca7/Community/Tdarr_Plugin_tws101_Ultimate_GPU_Transcoder_HDR.js) plugin. Credit goes to them for creating the main parts of this plugin. I just heavily tweaked it for higher quality encodes with even smaller sizes, added the tagging function, made HDR optional, and added some other various edits. 

This plugin will transcode H264 or reconvert HEVC files using NVENC with bframes, 10bit, and (optional) HDR. Requires a Turing NVIDIA GPU or newer. 
If reconvert HEVC is on and the entire file is over the bitrate filter, the HEVC stream will be re-encoded. Typically results in a 20-55% smaller size with very little quality loss.

This plugin is designed for processing entire movie libraries, HDR content and all. However, it's not recommended you actually use this to reconvert HDR files as it strips some HDR10/+/Dolby Vision metadata and leaves just PQ. The reconvert_hdr option is more meant to filter out these files rather than actually convert them.

Because of the heavily tweaked ffmpeg encoder settings, HEVC to HEVC reconverting usually results in a higher bitrate than the target bitrate, but much less than the original. This plugin implements the filter_by_stream_tag plugin to prevent infinite loops caused by that higher bitrate being above target bitrate.

By default, all settings are ideal for most use cases

Example screenshots below. You can click on the pictures and zoom in to get a feel for the (very minimal) difference in quality-

![Screenshot 2023-12-31 152131](https://github.com/PronPan/Tdarr-H264-HEVC-to-NVENC-with-Optional-HDR/assets/5284391/619f1b39-b814-4b1f-b8c7-2ae07416d5a7)

![Screenshot 2023-12-31 152201](https://github.com/PronPan/Tdarr-H264-HEVC-to-NVENC-with-Optional-HDR/assets/5284391/ddabcd0a-ffc6-43a5-898a-cdbcb3dd665c)

![Screenshot 2023-12-31 152216](https://github.com/PronPan/Tdarr-H264-HEVC-to-NVENC-with-Optional-HDR/assets/5284391/5a201de8-b878-439b-b229-f5b5d257ea2c)
