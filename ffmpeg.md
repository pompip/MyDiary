# ffmpeg

## usb 摄像头

> linux

1. preview  ffplay /dev/video0

2. recoard ffmpeg -i /dev/video0 /tmp/1.mp4

> windows
ffplay -f dshow -i video="Integrated Camera"
