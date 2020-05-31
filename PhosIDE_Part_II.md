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


## PhosIDE in Action

1. Move the cursor to the bottom of Jitsi View window so that the toolbox buttons appear. Click on the chat panel button to activate the chat panel, as shown in figure 4. Click on the "More actions" button at the right to get the submenu as shown in figure 5, then click "blur my background". This will activate the TensorFlow BodyPix algorithm in [`JitsiStreamBlurEffect.js`](https://github.com/udexon/jitsi-phoshell/blob/master/react/features/stream-effects/blur/JitsiStreamBlurEffect.js).

- Figure 4
<img src="https://github.com/udexon/Phoshell/blob/master/jitsi_phoshell/chat_arrows.png" width=600>


- Figure 5
<img src="https://github.com/udexon/Phoshell/blob/master/jitsi_phoshell/blur_background.png" width=600>

In figure 6, from lines 140 to 150, we have added code to copy variables from `JitsiStreamBlurEffect.js` to the global Phos stack `window.S`, so that we can paste the TensorFlow BodyPix mask image to `id="chatconversation` by executing Phoscript commands in `id="chatconversation` as well as the browser console, as show in figure 2 above.

- Figure 6
<img src="https://github.com/udexon/Phoshell/blob/master/jitsi_phoshell/colon_prefix_word.png" width=600>

