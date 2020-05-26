# Phoshell: The Ultimate Integrated Development Environment

Integrated Development Environment is perhaps the second most frequently used tool by programmers, after the ubiquitous shell.

- What if we combine the best features of IDE and shell together?

<img src="https://github.com/udexon/Phoshell/blob/master/jitsi_phoshell/chatconversation.png" width=600>

The screenshot above shows the `id="chatconversation"` panel in Jitsi Meet web client (running in Chromium) on the right and the browser console on the left.

We have modified [`ChatMessage.js`](https://github.com/udexon/jitsi-phoshell/blob/master/react/features/chat/components/web/ChatMessage.js) so that Phoscript commands (a stack machine / Reverse Polish Notation script language derived from the Forth programming languge) can be entered in chat box and the `id="chatconversation"` panel can be used as graphical output display for debugging purpose. Our goal is: 
- to modify Jitsi Meet to make it an Augmented Reality conferencing app where human figures from video streams will be converted into avatars and placed in 3D room, simulating meetings in 3D environment.

The Phoscript words ("functions" in Forth terminology) that were entered are:
- `yellow:` Change the colour of the text of the last `usermessage` (ClassName) to yellow.
- `yellow:`
- `blue:` Change the colour of the text of the first `usermessage` (ClassName) to blue. Default value is red, as specified in [`_chat.scss`](https://github.com/udexon/jitsi-phoshell/blob/master/css/_chat.scss)
- `33 66 +` Evaluate `33 + 66` in Reverse Polish Notation. The output is displayed in the browser console by inspecting variable `S` (stack), where the top of stack (TOS, last element in the array S) is now `99`.

The Phoscript words are specified in [`phos.js`](https://github.com/udexon/jitsi-phoshell/blob/master/phos/phos.js):

<img src="https://github.com/udexon/Phoshell/blob/master/jitsi_phoshell/Phoscript_words.png" width=600>

The Phoscript words are evaluated with the following JavaScript function call at line 39 of `ChatMessage.js`:

- `window.S[0].F( content[0] );`

The first (bottomost) item of the stack `S[0]` is an object of the class `Phos`, defined in `phos.js`, which has an entry point function `F()` that takes a space delimited string containing Phoscript words and tokens.
