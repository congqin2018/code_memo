# change encoding recursively
```
for files in ./**/*.sql; do   iconv -f sjis -t UTF-8 "$files" > "convert/$(basename "$files")"; done
```

# vscode regex  
```
// 1. → //## 1.

^(\s*)//([^#].*\d)
↓
$1//##$2
```

```
* [xx] → * <p>[xx]</p>

\*\s\[(.+)$
↓
* <p>[$1</p>
```

```
remove //##//xxxxxxx

//##//.*$\n
↓
<empty>
```
