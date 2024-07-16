# Digremoji

Pronounced:  Die - Grim - oji

### What is it?

A simple digraphical substitution cipher. It encodes text by mapping every possible pair of letters to a specific emoji. It can encode only letters and spaces. Letter case is lost, the message will always come out in all lower or upper case regardless of the input state.


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
If the message has an odd number of characters then a space is added to the end so that all chunks are exactly 2 characters.

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

Most importantly it was amusing and interesting to me. I was learning about ciphers that used digrams and wanted to do something a bit "hands on" so I created this.
