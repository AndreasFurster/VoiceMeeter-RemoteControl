# VoiceMeeter-RemoteControl
Basic remote control VoiceMeeter over LAN. This application will not support all features of VoiceMeeter and will not stream sound to the host pc. Use VBAN for that. 

## VoiceMeeterRemoteControl.Host
This is a Windows Service that listens to clients and controls a VoiceMeeter installation. 

## VoiceMeeterRemoteControl.Client
This is a simple WPF application to control the host pc.
Config is located at `C:/VoiceMeeterRemoteControl/config.json`.

### Config.json
```json
{
  "host": "192.168.1.20",
  "commands": [
    {
      "name": "Mute",
      "requests": [
        { "type": "setVolume", "value": -60, "input": "A1" },
        { "type": "setVolume", "value": -60, "input": "A2" },
        { "type": "setVolume", "value": -60, "input": "A3" }
      ]
    },
    {
      "name": "Lower volume",
      "requests": [
        { "type": "ajustVolume", "value": -5, "input": "A1" },
        { "type": "ajustVolume", "value": -5, "input": "A2" },
        { "type": "ajustVolume", "value": -5, "input": "A3" }
      ]
    },
    {
      "name": "Play from my pc",
      "requests": [
        { "type": "setVolume", "value": -60, "input": "A1" },
        { "type": "setVolume", "value": -60, "input": "A2" },
        { "type": "setVolume", "value": 0, "input": "A3" }
      ]
    }
  ]
}

```
