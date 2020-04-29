# ffmpeg

## usb 摄像头

### linux

* preview

```shell
ffplay /dev/video0
```

* recoard

```shell
 ffmpeg -i /dev/video0 /tmp/1.mp4
```

### windows

ffplay -f dshow -i video="Integrated Camera"
