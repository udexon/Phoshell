# Phoshell: The Ultimate Integrated Development Environment

Integrated Development Environment is perhaps the second most frequently used tool by programmers, after the ubiquitous shell.

- What if we combine the best features of IDE and shell together?

<img src="https://github.com/udexon/Phoshell/blob/master/jitsi_phoshell/chatconversation.png" width=600>

The screenshot above shows the `id="chatconversation"` panel in Jitsi Meet web client (running in Chromium) on the right and the browser console on the left.

We have modified [`ChatMessage.js`](https://github.com/udexon/jitsi-phoshell/blob/master/react/features/chat/components/web/ChatMessage.js) so that Phoscript commands (a stack machine / Reverse Polish Notation script language derived from the Forth programming languge) can be entered in chat box and the `id="chatconversation"` panel can be used as graphical output display for debugging purpose. Our goal is: 
- to modify Jitsi Meet to make it an Augmented Reality conferencing app where human figures from video streams will be converted into avatars and placed in 3D room, simulating meetings in 3D environment.
