In the following video, we demonstrated how Jitsi Meet BodyPix mask image can be displayed in the chat panel (`id="chatconversation"`) on a rotating cube using `three.js CanvasTexture`: 

https://raw.githubusercontent.com/udexon/Phoshell/master/PhosIDE_part_III/blur_sway_camy.webm

This is a critical step towards implementing an Augmented Reality Conferencing app, Phoom, a significant breakthrough from the current mainstream video conferencing apps such as Zoom and Jitsi Meet.

In addition, we introduce Phoscript, a highly flexible script derived from the Forth programming language, which we believe can greatly simplify the complex `three.js` JavaScript syntax, and help the average programmers in mastering various tricks required involving these various support tools:
- TFJS BodyPix (TypeScript)
- `three.js` WebGL (JavaScript)
- Jitsi Meet (React Redux)

At 00:00, on the right of the screen is a white silhouette covering the head and shoulders of subject X, produced by [`drawMask()`](https://github.com/udexon/tfjs-models/blob/master/body-pix/src/output_rendering_util.ts) in TFJS Bodypix. 

<img src="https://github.com/udexon/Phoshell/blob/master/PhosIDE_part_III/sway_00.png" width=600>

In the original `@jitsi/jitsi-meet`, `_renderMask()` calls `bodyPix.drawBokehEffect()` (line 80).

https://github.com/jitsi/jitsi-meet/blob/master/react/features/stream-effects/blur/JitsiStreamBlurEffect.js

We have replaced it with `bodyPix.drawMask()` as shown below:

<img src="https://github.com/udexon/Phoshell/blob/master/PhosIDE_part_III/drawMask.png" width=600>

We have forked `@jitsi/jitsi-meet` as `@udexon/jitsi-phoshell`. Due to continuous changes to the test code, we have not updated the latest code in our reporsitory. However, we believe expert developers will be able to reproduce the modifications by following instructions in this tutorial. Less experienced developers may also contact us for more detailed instructions and latest sample code. 

https://github.com/udexon/jitsi-phoshell

 / Phoshell / PhosIDE
