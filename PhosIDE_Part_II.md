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

2. In figure 6, from lines 140 to 150, we have added code to copy variables from `JitsiStreamBlurEffect.js` to the global Phos stack `window.S`, so that we can paste the TensorFlow BodyPix mask image to `id="chatconversation` by executing Phoscript commands in `id="chatconversation` as well as the browser console, as show in figure 2 above.

- Figure 6
<img src="https://github.com/udexon/Phoshell/blob/master/jitsi_phoshell/colon_prefix_word.png" width=600>

3. The commands entered were:

- In chat panel:            
```
:b 5 [flipHorizontal,maskBlurAmount,opacity,mask,this._inputVideoElement] :v
```

- In console: 
```js
var x = document.createElement("CANVAS");
var c = document.getElementById("chatconversation");
c.appendChild(x)               
S.push(x)

S[0].F("mrsz:") 
```

4. As shown in figure 7, lines 70 to 96 have been added to [`ChatMessage.js`](https://github.com/udexon/jitsi-phoshell/blob/master/react/features/chat/components/web/ChatMessage.js) to process the Phoscript command above.

- Figure 7
<img src="https://github.com/udexon/Phoshell/blob/master/jitsi_phoshell/chat_prefix_colon.png" width=600>


`:b` (`b` for "begin") is a flag for `ChatMessage.js` to treat the subsequent string as Phoscript command.

`5` is an arbitrary number that is stored as `S[1]` of the global stack, as a sort of line number for executing commands, that can be used as mutex in asynchronous environment such as JavaScript. Tentatively, we employ a simple criterion here that is the current line number must be greater than the existing number stored in `S[1]` for the current command to be executed.

The following is an array of variables (no space is allowed for this simple version of variable extraction) to be extracted from `JitsiStreamBlurEffect.js`:

```js
[flipHorizontal,maskBlurAmount,opacity,mask,this._inputVideoElement]
```

`:v` is the colon prefix word (word as in Forth terminology for function name) to execute `eval(eval(expr))` on the previous token.

5. The following commands are executed in the browser console:
```js
var x = document.createElement("CANVAS");
var c = document.getElementById("chatconversation");
c.appendChild(x)               
S.push(x)

S[0].F("mrsz:") 
```
A new canvas element `x` is created and appended to `id="chatconversation"`.

`S[0].F()` which is the entry point to Phoscript is called to execute `mrsz:` which is mapped to `drawMaskResize()` from [TFJS BodyPix](https://github.com/udexon/tfjs-models/blob/master/body-pix/src/output_rendering_util.ts). The original repository only has a `drawMask()` function that did not resize the input image when calling `drawImage()`. We have made the modifications (lines 432 and 420) as show in figure 8.

- Figure 8
<img src="https://github.com/udexon/Phoshell/blob/master/jitsi_phoshell/tfjs_drawMaskResize.png" width=600>






