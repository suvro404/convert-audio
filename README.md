## convert-audio
##### A lightweight audio conversion tool to convert mp3, wav and aac file.

### [DEMO](https://suvro404.github.io/convert-audio-playground/)

#### Install
```
npm install convert-audio
```

### Usage
```
import AudioConverter from 'convert-audio'

AudioConverter.convert(sourceAudioFile, targetAudioFormat);
```

### Example Code
```
<input type='file' accept=".mp3, .wav, .aac" onchange="convertAudio(this)" />

import AudioConverter from 'convert-audio'

async function convertAudio(input) {
    let sourceAudioFile = input.files[0];
    let targetAudioFormat = 'wav'
    let convertedAudioDataObj = await AudioConverter.convert(sourceAudioFile, targetAudioFormat);
}
```
##### This convert function will return a converted audio data object which includes audio name, format and blob URL.
##### This blob URL can be used to download the converted audio.

```
function downloadAudio(convertedAudioDataObj) {
    let a = document.createElement("a");
    a.href = convertedAudioDataObj.data;
    a.download = convertedAudioDataObj.name + "." + convertedAudioDataObj.format;
    a.click();
}
```


### License
MIT