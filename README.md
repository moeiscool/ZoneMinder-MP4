# What is CCTV? What is Open Source?
CCTV stands for Closed-Circuit Television. It's also a fancy way of saying DVR, Digital Video Recorder. It's a system in which multiple cameras can be watched or recorded for either personal or business circumstances.

Open Source means it is open for editing to your liking... and the way its being made. It will not be difficult. There are no arbitrary libraries, like mootools, to get in your way. Be aware that open source does not mean free. Shinobi just happens to be free as well.

# What is the aim of Shinobi
Shinobi can be used as a Baby Monitor, Construction Site Montage Viewer, Store Camera DVR, and much more. I suppose the simplest way of saying it is *As Magento is to eCommerce, Shinobi is to CCTV.*

**A Quick Look at Shinobi <a href="https://www.youtube.com/watch?v=Z2hr5E8w8Q8">YouTube</a>**

<img src="https://github.com/moeiscool/Shinobi/raw/master/web/libs/img/demo.gif">

**Noted Aspects**
- Records IP Cameras and Local Cameras
- Streams by WebSocket
- Save to WebM and MP4
 - Other formats will be added after codec choices are less confusing.
- API
 - Get videos
 - Get monitors
 - Change monitor modes : Disabled, Watch, Record
 - Embedding streams

# Why make this? Other solutions already exist.

ZoneMinder was the first choice but it proved unstable. A few reasons are mentioned below. Solutions such as ispyconnect are not relevant as they have a cost for using their platform.

- **MJPEG streams are beyond unusable in modern applications.**
    - Essentially with MJPEG you are opening a new stream everytime you create an image with an MJPEG url. Even if you remove this element it will continue to eat resources from the server and client. Only way to deal with it currently is through an `iframe` or `popup`. Neither of which should be considered acceptable.
    - Shinobi addresses this with `WebSocket` streams. As frames are captured by FFMPEG they are base64 encoded and sent to the client.
    
- **JPEG Storage is just a terrible idea.**
    - Saving each frame as a separate file in JPEG format can have a seriously detrmental effect on storage space and the hardware itself. Hardware is more likely to fail under the stress of continuously saving frames to storage.
    - Shinobi saves to WebM and MP4 files. While MP4 takes a fair amount of space.. its level of CPU usage during encoding for H.264 streams is just amazing.

- **Using languages that are not needed.**
    - You'll find that ZoneMinder uses multiple languages to achieve very small results. This probably just because of the time it was written in... but with that said all the devs currently working on it should have addressed these issues and removed unecessary steps, languages, and files. ZoneMinder uses Perl, PHP, JavaScript, C, HTML, CSS, MySQL, and probably more.
    - Shinobi uses JavaScript, HTML, CSS, and MySQL. Simple right? It should be.

- **Using outdated or troublesome libraries.**
 - Mootools, need I say more? and the API is done with an added library called CakePHP... just.. why? Both libraries should have been replaced already with faster and modern solutions.

- **Outdated methods**
 - Continuously hammering the database is not a good idea. It should already have had websockets added and interval refreshes removed completely before 2014.

**These are just some reasons why Shinobi had to be born.** I couldn't wait any longer and the thought of donating to a team that ignores 4(+) year old issues seemed like a fools bet.

# Take this into perspective
Shinobi is a program that can do MP4 and WebM recording with MJPEG, JPEG, H264 Cameras and WebSocket streams. I compiled these features in less than 2 months. **Alone. No funding.**

Zoneminder devs couldn't get MP4 recording into the master branch and its been 4 years since they started working on it. While **+70 devs** and gaining **+$1200/month** in donations.

**Yep.** You decide what all that means and *this is only the tip of the iceberg.*

"*Sounds like a lot of complaining? Yah, I know. So I went and did something about it.*"

<a href="https://github.com/moeiscool/Shinobi/wiki/Supported-Systems">Supported Systems</a>

<a href="https://github.com/moeiscool/Shinobi/wiki/Install">How to Install and Run</a>


# Author

Moe Alam

Follow me on <a href="https://twitter.com/moe_alam">Twitter</a>

Find me on <a href="https://shinobicctv.herokuapp.com/">Slack</a>! :) 

# Help make Shinobi the best Open Source CCTV platform.

If you like Shinobi please check out some *<a href="https://github.com/moeiscool/Shinobi/wiki/Support-Shinobi">ways you can help support Shinobi</a>*.
