intro :


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

| Context                  | Best Algorithm                        |
| ------------------------ | ------------------------------------- |
| Simplicity               | Huffman                               |
| Legacy compression       | DEFLATE / GZIP                        |
| Modern web               | Brotli (better ratio for JS/CSS/HTML) |
| General file compression | GZIP or Brotli                        |

---
## Huffman
lossy compression coding algorithm that code the input text with shorter 0,1 code .
for each character assign a binary code. characters with more frequently, have shorter code.

- Created by David Albert Huffman
- Use Greedy algorithm (fast, simple and easy to implement)
- and its used as base algorithm in many other compression algorithm.
- For more information, search **Shannon** Theory

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
     /       \ 
	(3)       (4)
	/  \     /   \ 
'n'    (2) 'f'   (2)
	  /  \       /   \
	'h'  'u'   'm'   'a'

```

'a' --> 0
'c' --> 10
'b' --> 11

Final code is : 01011.

- for creating the code, it uses the DFS algorithm , which mean, walk through each node
- for decoding , it search bit by bit based on the codebook which is shared between two beforehand.

----
## Lempel Ziv
Store the pointer to where it appeared before.
token / output (offset, length, next character)

example :
TO BE OR NOT TO BE --> TO BE OR NOT <12 , 5 , 0> 


----
## Brotli

Developed by Google, introduced in 2015.  
Designed primarily for web compression, especially for HTTP compression (like compressing HTML, CSS, JavaScript).  
Aimed to provide better compression ratios than Gzip and faster decompression.

Used in : http, WOFF2, APK, Chrome assets

### Core :
- LZ77 : find repeated characters (but brotli use a custom, and optimized version of it )
- Context modeling : predict next bytes based on patterns
- Huffman coding : Encode bytes with shortest code
