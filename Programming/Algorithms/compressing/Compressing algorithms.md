
----

Reduce size of data to occupy less space in storage.

there is two type :
- Lossy (irreversible)
- Lossless (reversible)

## Lossy (irreversible)
discard some data and sometimes its not imperceptible to the user.
#### Types:
- DWT (Discrete Wavelet Transform)
- DFT (Discrete Fourier Transform)
### In used

- JPEG & Webp (math stuff and divide image into 8*8 pixels and replace same near pixels with one big block)
- MP3 & Mobile Voice talking & Telegram and other socials
- H264 & H265 (analyze how humans perceive video and remove information that are less noticeable to the eye for example in blu-rays , bitrate is high and humans cant tell the difference) & video streaming.

---

## Lossless (reversible)
compressed data = decompressed data , preserve all original data.

#### Types:
- RLE (Run Length Encoding)
- **Huffam**
- **Lempel-Ziv** (LZ77, LZ78, LZW, ...)
- **Brotli** ( combines LZ77, Huffman, Context modeling)
- Deflate (combines LZ77, Huffman)
- Gzip (Deflate + headers and etc.)


---
## Huffman
lossy compression coding algorithm that code the input text with shorter 0,1 code .
for each character assign a binary code. characters with more frequently, have shorter code.

- Created by David Albert Huffman
- Use Greedy algorithm (fast, simple and easy to implement) (A **greedy algorithm** is a method for solving optimization problems by making the best choice at each step,)
- and its used as base algorithm in many other compression algorithm.
- For more information, search **Shannon** & **Entropy** Theory

Goal :  
Minimize the total number of bits that used to represent a sequence of symbols. 

### How it works ?

1. Calculate how often each symbol is appears
2. Use Priority queue and create tree 
```
	[1, 'c']  ← leaf node (symbol 'c', frequency 1)
	[2, 'b']  ← leaf node (symbol 'b', frequency 2)
```
pop two smallest, merge and push back to the top.
```
[3,'a'], [3,['c','b']]
```
and repeat this until there is on node that represent the full Huffman tree root.
3. Assign binary codes to each character
note : left leaves are 0 , and right consider as 1

```
        (7)
     /        \ 
	(3)        (4)
   /  \       /   \ 
'n'    (2)  'f'   (2)
	  /  \       /   \
	'h'  'u'   'm'   'a'

```

'a' --> 0
'c' --> 10
'b' --> 11

Final code is : 01011.

- for creating the code, it uses the DFS algorithm , which mean, walk through each node
- for decoding , it search bit by bit based on the codebook which is shared between two beforehand.
- changing the position of the left and right movement value does not affect to the final prefixes
  because it again going to create the prefix-free codes and only for decoding we should have the same movement pattern.
- receiver gets information about the decoding from request headers,

Accept-Encoding: Gzip, deflate, br 
content-encoding: Gzip ,deflate, br


----
## Lempel Ziv
These algorithms aim to reduce the size of data by identifying and eliminating redundancy.
Store the pointer to where it appeared before.
introduced by Abraham Lempel and Jacob Ziv.

example :
token / output (offset, length) < j , L>
TO BE OR NOT TO BE --> TO BE OR NOT <12 , 5>.

Buffer : all searched and visited characters
Search: empty

walk trough the buffer, and search for each character in the search list, and it could not found it at 
first, and push it in

[T,O, , B] search in it
it want to always replace the longest characters, for example, it reach to T, but next character is not in buffer

so it not replace it. characters in buffer should be only Contiguous and not separate.

where is it used :
- GIF (LZW)
- PNG (LZ77)
- etc.


----
## Brotli

Developed by Google, introduced in 2015.  

Designed primarily for web compression, especially for HTTP compression (like compressing HTML, CSS, JavaScript).
Brotli is dynamic and adapt itself via the input data.

Aimed to provide better compression ratios than Gzip and faster decompression.
Used in : http, WOFF2, APK, Chrome assets

### Core :
- 1) LZ77 : find repeated characters (but brotli use a custom, and optimized version of it )
- 2) Huffman coding : Encode bytes with shortest code
- 3) Unlike Huffman that generate code for each characters, by using context modeling, it guess what the next character code could be. look back to the produced codes then generate new one. (The is repetitive, and when it hit to the T, it can guess that its going to be h next, and create for it and assign shorter code to it)


where is it used :
- HTTP compression for webpages. (supported by modern browsers)
- Web fonts compression.(server can compress it and send smaller size)
- etc.


---

[LZW geeksforgeeks](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://www.geeksforgeeks.org/lzw-lempel-ziv-welch-compression-technique/&ved=2ahUKEwislonp2c-NAxXWhv0HHU4pCCcQFnoECBoQAQ&usg=AOvVaw2VjEGbtLA2Ia47Z6Uv8vd7)
[Lempel Ziv Algorithm](https://www.youtube.com/watch?v=hHQgu4qILGs)
[Wiki-Data Compression](https://en.wikipedia.org/wiki/Data_compression)
[Shanon Theory](https://en.wikipedia.org/wiki/Shannon%E2%80%93Hartley_theorem)
[Entropy](https://en.wikipedia.org/wiki/Entropy_coding)
[Lossy Compression](https://en.wikipedia.org/wiki/Lossy_compression)
[Lossless Compression](https://en.wikipedia.org/wiki/Lossless_compression)
[How Computers Compress Text: Huffman Coding and Huffman Tree](https://youtu.be/JsTptu56GM8?si=Fe7kl-tMnEA8lSNv)
[Elegant Compression in Text(The LZ77 Method)](https://youtu.be/goOa3DGezUA?si=4mggP48yNYL3aWhN)
[How Huffman Trees Work](https://youtu.be/umTbivyJoiI?si=kD9mjiTveDYfrk6h)


