# Git in Depth
## Git Fundations
### #Git Storage
how Git stores information comparing it to a key-value store where data is the value and the hash of the data is the key. This system is also known as content-addressable storage, which is when the content to generate the key.
- you can then use the key to retrieve the content
- the key it's called a SHA1, is cryptographic hash function given a piece of data.
- it produces a 40-digit hexadecimal number and this value should always be the same if the given input is the same
