# Why not to use ZoneMinder
ZoneMinder was the first choice for CCTV and NVR but it proved unstable. A few reasons are mentioned below.

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
 - Having to tip toe and continuously fix the mistakes of other developers is not how development should be. I should be able to download ZM and start editing it to the way i need. Why else is it open source? So people can commit random things?

- **Delaying more than necessary**
 - Zoneminder has +70 devs and gaining +$900/month in donations.. they should have gotten somewhere with all of these issues if not eliminated them at least 4 years ago.
 - The excuse "I only work on this in my free time" is one used too often. Of course we are aware it's done in free time. We want an explanation why you couldn't or a theoretical solution, not an excuse why you didn't want to try.

**These are just some reasons why Shinobi had to be born.** I couldn't wait any longer and the thought of donating to a team that ignores 4(+) year old issues seemed like a fools bet.

Try the replacement to ZoneMinder instead and save yourself the nightmare that is zoneminder.
https://github.com/moeiscool/Shinobi
