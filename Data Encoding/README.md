# Data Encoding

This room explains how computers represent text using character encodings. It covers ASCII, Unicode, UTF-8, UTF-16, UTF-32, and how encoding problems can cause text to appear as gibberish.

## Topics Covered

* ASCII
* Unicode
* UTF-8
* UTF-16
* UTF-32
* Unicode code points
* Emoji encoding
* Character encoding compatibility
* Encoding-related gibberish

## ASCII

ASCII stands for American Standard Code for Information Interchange.

The original ASCII standard uses 7 bits and defines 128 characters, including:

* Uppercase and lowercase English letters
* Numbers
* Punctuation
* Control characters

Examples:

```text
A → 65 → 0x41 → 01000001
a → 97 → 0x61 → 01100001
0 → 48 → 0x30 → 00110000
@ → 64 → 0x40 → 01000000
```

ASCII can represent basic English text, but it cannot represent characters from many other languages or emojis.

For example, the text `TryHackMe` can be represented in hexadecimal as:

```text
54 72 79 48 61 63 6b 4d 65
```

Each hexadecimal value corresponds to an ASCII character.

## Unicode

Unicode was created to provide a universal way of representing characters from different writing systems.

Examples of Unicode code points:

```text
A  → U+0041
Ω  → U+03A9
あ → U+3042
☕ → U+2615
```

Unlike ASCII, Unicode can represent characters from many different languages, symbols, and emojis.

## UTF-8

UTF-8 is one of the most common Unicode encoding formats, especially on the Web.

It uses between 1 and 4 bytes depending on the character.

ASCII characters use exactly one byte in UTF-8, which makes UTF-8 backwards compatible with ASCII.

Examples:

```text
A → U+0041
Ω → U+03A9
🔥 → U+1F525
```

More complex characters can require multiple bytes.

## UTF-16

UTF-16 normally uses 2 bytes for a character, but characters outside the Basic Multilingual Plane require a surrogate pair, using 4 bytes in total.

For example:

```text
シ → U+30B7
```

An emoji such as `🔥` requires a surrogate pair in UTF-16:

```text
U+D83D U+DD25
```

## UTF-32

UTF-32 is simpler because every Unicode code point uses exactly 4 bytes.

For example:

```text
A  → U+00000041
😌 → U+0001F60C
🔥 → U+0001F525
```

This makes UTF-32 straightforward, but it also uses more storage than UTF-8 or UTF-16.

## Encoding Problems

Text can appear as strange or incorrect characters when it is saved using one encoding and later interpreted using another.

For example, different ISO-8859 encodings were created for different groups of languages. A character saved using one encoding may be interpreted as a completely different character when opened using another encoding.

Unicode and modern encodings such as UTF-8 help avoid these compatibility problems.

## Key Takeaways

* ASCII uses 7 bits and supports 128 characters.
* Unicode assigns a unique code point to characters.
* UTF-8 uses 1 to 4 bytes.
* UTF-16 uses 2 or 4 bytes.
* UTF-32 always uses 4 bytes.
* ASCII characters are directly compatible with UTF-8.
* Emojis are Unicode characters and can require multiple bytes depending on the encoding.
* Using the wrong encoding can result in corrupted or unreadable text.

## Conclusion

This room helped me understand how text is represented at the binary level and how character encodings allow computers to interpret those numbers as readable characters.

The main concept is that a character has a Unicode code point, while UTF-8, UTF-16, and UTF-32 are different ways of encoding that code point into bytes.
