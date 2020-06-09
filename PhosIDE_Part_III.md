# PhosIDE Part III: ....

1. In the following video, we demonstrated how Jitsi Meet BodyPix mask image can be displayed in the chat panel (`id="chatconversation"`) on a rotating cube using `three.js CanvasTexture`: 

https://raw.githubusercontent.com/udexon/Phoshell/master/PhosIDE_part_III/blur_sway_camy.webm

This is a critical step towards implementing an Augmented Reality Conferencing app, Phoom, a significant breakthrough from the current mainstream video conferencing apps such as Zoom and Jitsi Meet.

In addition, we introduce Phoscript, a highly flexible script derived from the Forth programming language, which we believe can greatly simplify the complex `three.js` JavaScript syntax, and help the average programmers in mastering various tricks required involving these various support tools:
- TFJS BodyPix (TypeScript)
- `three.js` WebGL (JavaScript)
- Jitsi Meet (React Redux)

2. a. At 00:00, on the right of the screen is a white silhouette covering the head and shoulders of subject X, produced by [`drawMask()`](https://github.com/udexon/tfjs-models/blob/master/body-pix/src/output_rendering_util.ts) in TFJS Bodypix (figure 1).

- Figure 1

<img src="https://github.com/udexon/Phoshell/blob/master/PhosIDE_part_III/sway_00.png" width=600>

In the original `@jitsi/jitsi-meet`, `_renderMask()` in  [`JitsiStreamBlurEffect.js`](https://github.com/jitsi/jitsi-meet/blob/master/react/features/stream-effects/blur/JitsiStreamBlurEffect.js) calls `bodyPix.drawBokehEffect()` (line 80).

We have replaced it with `bodyPix.drawMask()` as shown below:

<img src="https://github.com/udexon/Phoshell/blob/master/PhosIDE_part_III/drawMask.png" width=600>

We have forked `@jitsi/jitsi-meet` as `@udexon/jitsi-phoshell`. Due to continuous changes to the test code, we have not updated the latest code in our reporsitory. However, we believe expert developers will be able to reproduce the modifications by following instructions in this tutorial. Less experienced developers may also contact us for more detailed instructions and latest sample code. 

https://github.com/udexon/jitsi-phoshell

- b.  The head and shoulders white silhouette on the right side of figure 1 is broader compared to the smaller head and shoulders white silhouette in the chat panel area (`id="chatconversation"`), as the latter has been distorted (squeezed) to fit to one of six sides of a cube in `three.js`.

The white silhouette in the chat panel stays static from 00:00s to 00:11s until the following command is entered in the browser console:

```js
S[0].F("15 int: N blur set:")
```

This command sets the value of `TP.N` to 15 as shown in the following code, which is part of `_renderMask()`.

<img src="https://github.com/udexon/Phoshell/blob/master/PhosIDE_part_III/TP_N.png" width=600>

It will execute the command stored in `TP.cmd` every time `_renderMask()` is called by `_onMaskFrameTimer()`. `TP.N` will be decremented by 1 each time and stops when `TP.N==0`.

`TP.cmd` is set by the following commands in the browser console:

```js
S[0].F("blur init:  canvas: canvas blur set:")
S.push('cvst: cube_cvst:    0.1 float: N blur get: mul: camy: scene:'); S[0].F("cmd blur set:")
```

 / Phoshell / PhosIDE
