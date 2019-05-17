### Cool regex


#### Java
Find/Replace annotations?
e.g.
- [@]JoinColumn\(name = "(.*)?"\)
- [@]OneToOne\(mappedBy = "(.*)?"\)


#### CSS
Find all class names
eg.
- (?:[\.]{1})([a-zA-Z_]+[\w-_]*)(?:[\s\.\{\>#\:]{1})
- /(?:[\.]{1})([a-zA-Z_]+[\w-_]*)(?:[\s\.\{\>#\:]{1})/igm (for use in javascript code)
- \burl\(\"(.*)?\"\) //find all url("")
-/^url\(["']?/, '').replace(/["']?\)$/          //find all url("")


