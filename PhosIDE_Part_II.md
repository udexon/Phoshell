# PhosIDE Part II: ....

In [a previous article](https://github.com/udexon/Phoshell/blob/master/Phoshell_Ultimate_IDE.md), we introduced PhosIDE, an IDE _embedded_ within Jitsi-Meet web client, a React Redux app, as shown in figure 1.

- Figure 1
<img src="https://github.com/udexon/Phoshell/blob/master/jitsi_phoshell/chatconversation.png" width=600>

In this article, we describe how we use PhosIDE to extract the TFJS mask image from [`JitsiStreamBlurEffect.js`](https://github.com/udexon/jitsi-phoshell/blob/master/react/features/stream-effects/blur/JitsiStreamBlurEffect.js) and paste it into `id="chatconversation"` in [`ChatMessage.js`](https://github.com/udexon/jitsi-phoshell/blob/master/react/features/chat/components/web/ChatMessage.js), as shown in figure 2.

- Figure 2
<img src="https://github.com/udexon/Phoshell/blob/master/jitsi_phoshell/jm_tfjs_mask.png" width=600>

Ultimately, our goal is to employ `three.js` video texture to make 2.5D and 3D avatars, and transform Jitsi-Meet into an Augmented Reality Conferencing app, as shown in figure 3 below.

- Figure 3
<img src="https://github.com/udexon/Phoshell/blob/master/jitsi_phoshell/threejs_video_texture.png" width=600>

