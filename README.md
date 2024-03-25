This is a blog where we try to explain poorly-explained things in an easier-to-understand way.
# Binary format
We use a custom format for representing binary blobs:
```bindef
"This is ASCII text"\r\n[NUL]
```
In this binary format all whitespace is ignored except for in text blocks.
- `"{text}"` - ASCII text.
- `{something}` - Insertion of some data.
- `\n`, `\r`, etc. - C-style escapes.
- `[{shortening}]` - Name of an ASCII character.
These blocks have the language set to `bindef`.