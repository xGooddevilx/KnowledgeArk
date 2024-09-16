# Edit Distance

I don’t know why, but one day, if you want to figure out how two words are different from each other, you can use this algorithm.

## How it works

Edit distance is like a **score**. It tells you how many changes you need to make to turn one word into another.

The changes can be:

1. **Insert** a letter (Insertion)
2. **Delete** a letter (Deletion)
3. **Replace** a letter (Substitution)

This algorithm counts the number of these steps needed to make the words the same.

### Examples

- Changing **"cat"** to **"cut"** requires 1 change:

  - Replace **'a'** with **'u'** → Edit distance = **1**

- Changing **"cat"** to **"bat"** requires 1 change:

  - Replace **'c'** with **'b'** → Edit distance = **1**

- Changing **"kitten"** to **"sitting"** takes more steps:
  - Several replacements and insertions → Higher edit distance

So yeah, it’s a way to measure how similar or different two words are based on how much you need to change them.

For more information, you can check out the [Wikipedia page on Edit Distance](https://en.wikipedia.org/wiki/Edit_distance).
