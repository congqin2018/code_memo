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
find **Aaaaa Bbbbb** (exclude **// TODO Aaaaa**)
```
^[^//<]+[A-Z]\w*\s[A-Z]
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
delete all java file containing a certain string
```
grep -lrIZ "co.nttcom.business.metasys.sg.domain.model.redefine.SgtSsg0421sRedefineDto" --include \*.java . | xargs rm
```
delete all line starting with a pattern
```
find . -name "*.java" | xargs sed -i -r '/^(\s|\t)*\/\/##/d;s/\s*\/\/##.*$//'
find . -name "*.java" -exec sed -i -r '/^(\s|\t)*\/\/##/d' {} +
```
