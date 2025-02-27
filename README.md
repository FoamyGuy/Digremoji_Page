# Digremoji

Pronounced:  Die - Grim - oji

[Live Demo](https://foamyguy.github.io/Digremoji_Page/)

### What is it?

A simple digraphical substitution cipher. It encodes text by mapping every possible pair of letters to a specific emoji.
It can encode only letters and spaces. Letter case is lost, the message will always come out in all lower or upper case
regardless of the input state.

### How does it work?

Every permutation of letters is assigned to a specific emoji.
e.g.

```
AA = 🍮
AB = 🚣
AC = 🚝
...
ZZ = 🌁
```

Space is also treated as a letter. All permutations of letter + space and vice versa are assigned emoji. (`'A '` = 📡).

The plain text message is split into chunks of 2 characters each, also known as digrams.
If the message has an odd number of characters then a space is added to the end so that all chunks are exactly 2
characters.

The cipher text is comprised of the emoji that represent all the digrams used in the original plain text message.

Example: Encode the text `"hello"`

Step 1:
`"hello"` has 5 letters which is an odd number, so we add a space to the end and make it `"hello "`

Step 2:
Split it into digrams, or chunks of length 2.
`"he", "ll", "o "`

Step 3:
Lookup the emoji for each digram

```
"he" = 📿
"ll" = 🤘  
"o " = 🐬
```

Step 4:
Combine the emoji to a string
`"📿🤘🐬"`

The encoded result is:
`"hello " = "📿🤘🐬"`

### Why?

Most importantly it was amusing and interesting to me. I was learning about ciphers that used digrams and wanted to do
something a bit "hands on" so I created this.

### Prior Art / Inspiration / Credits

- [Mozilla Codemoji](https://foundation.mozilla.org/en/campaigns/codemoji/) A page Mozilla published circa 2016 with a
  similar emoji substitution cipher
- [Emoji-Aes](https://aghorler.github.io/emoji-aes/) Encrypt a message with AES and then substitution cipher the base64
  with emoji
- [Face64](https://face64.me/) Base 64 encoding that uses emoji instead of upper and lower alphabet
- [PlayFair Cipher](https://en.wikipedia.org/wiki/Playfair_cipher) The digram substituion cipher I was learning about
  when I went down the rabbit hole that led to this existing
- [SplitMatrix32 PRNG](https://stackoverflow.com/a/47593316/507810) JS implementation of a pseudo random number
  generator that accepts seed values.