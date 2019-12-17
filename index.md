# Kodi Connect - Alexa

Implements [Alexa Video Skill](https://developer.amazon.com/docs/video/understand-the-video-skill-api.html)<br/>
Example [Youtube](https://www.youtube.com/watch?v=BTgooV_YEvg)

## Steps to set up Kodi Alexa integration
Please follow the tutorial [here](tutorial.md)

Please join Discord if you have any questions regarding setup, or in general<br/>
[*Discord link*](https://discord.gg/ryVcz7S)

## Working features
- Search and Display [Examples](https://developer.amazon.com/docs/video/video-skill-testing-guide.html#search-content)
  - This will display a list of matched Movies/TVshows
- Search and Play [Examples](https://developer.amazon.com/docs/video/video-skill-testing-guide.html#play-content)
- Control playback [Examples](https://developer.amazon.com/docs/video/video-skill-testing-guide.html#control-playback)
- Seeking [Examples](https://developer.amazon.com/docs/device-apis/alexa-seekcontroller.html#adjustseekposition)
- [Setting](https://developer.amazon.com/docs/device-apis/alexa-speaker.html#setvolume) and [Adjusting](https://developer.amazon.com/docs/device-apis/alexa-speaker.html#adjustvolume) volume, and [muting, unmuting](https://developer.amazon.com/docs/device-apis/alexa-speaker.html#setmute)
- Turning On/Off - "Alexa, turn On/Off <device_name>" (Device name is taken from KodiConnect page)
  - This is only available for devices with CEC capability, like RPi, etc. (it checks for `cec-client` binary)

**Note**: If updating Addon which introduces new features, you need to relink the Kodi device in Alexa app. Just unlink the device, and go through discovery again. This is because new versions of Addon now report supported features, to ensure backward compatibility, and seamless user experience. This should be the first step, if some of the features is not working for you.

## Donation
If you want to buy me a beer :) 

[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=X8AL7A9B6XMQ4)
