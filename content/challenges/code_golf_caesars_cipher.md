---
title: "Challenge 6: Code Golf: Caesar's Cipher"

draft: false
date:        "2015-03-20"
publishdate: "2015-03-20"

summary: |
    This challenge consists of encrypting and decrypting a short message using the Caesar Cipher with a selectable key.<br>
    **Paradigm:** _Structured Programming_<br>
    **Difficulty Level:** _Intermediate_
---

## Challenge 6: Caesar's Cipher Code Golf

This challenge consists of encrypting and decrypting a short message using the Caesar Cipher with a selectable key.<br>
**Paradigm:** _Structured Programming_<br>
**Difficulty Level:** _Intermediate_

Your program should be able to receive information from the command-line invocation, including the following arguments:

1. **Mode**:  either the word "encrypt" or the word "decrypt"
2. **Key**:   The cipher shift key - for example, the classic Caeser cipher shifts "a" to "d" 
    (a shift of 3), so you would supply the key 'd'.  
    You could also think of this as the letter that 'a' should be shifted to.
3. **Message**: The message follows the "Key" argument.  The message may contain spaces, so it 
    may be many "words", meaning that from the program's point of view it may continue for
    any number of additional arguments.

### Example usage:

**To encrypt:**

`caeser  encrypt  key  plaintext message`

**To decrypt: **

`caeser  decrypt  key  ciphertext message`

The following animation shows the program's expected behavior:

![caesar program example](/images/caesar.gif)

### Code Golf

Once you have the program working, try to make it as short as possible.  The shortest program (in terms of number of characters (bytes) in the source code file) that is able to solve the problem correctly wins!

