# RNBO Webpage Sampling Example

This sample code records the browser's audio input and plays it in MIDI.

You can access it here to see how it works.
https://tngsk.github.io/rnbo.sampling_test/

Try changing your browser's audio input settings.

# Code Changes

Referring to the following page, we added code to create a media stream and connect it to the RNBO device.

https://rnbo.cycling74.com/learn/working-with-web-audio-contexts

```javascript
// Connect mic-input to the device.node
navigator.mediaDevices
  .getUserMedia({ audio: true, video: false })
  .then((stream) => {
    UserMediaSource = context.createMediaStreamSource(stream);
    UserMediaSource.connect(device.node);
  });
```

# Requires a secure connection

When hosting a web page exported by RNBO　Web Export, it must be accessible via https. Otherwise, the external input will probably not work.
