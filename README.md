# vala.vim

This is a Vim plugin that provides [Vala][vala] file detection, syntax highlighting and more.

`vala.vim` contains a Vim syntax, indent and ftdetect files for Vala.

The base version has been imported directly from the [official site][vala-vim].

Some of the improvements over the base version are listed below.

## Syntax highlighting

* Methods ()
* Arrays, lists and hash tables as in `Array<int>`, `List<string>` and `HashTable<string, int>`
* Operators and Delimiters: `+`, `-`, `*`, `/`, `=`, `( )`, `[ ]`, `{ }`...
* String formatting in `printf`-like methods: `%d`, `%f`, `%s`, `%c`, `%u`, `%%`...

## Indentation

* Properly indents `namespace` sections, as well as ``

## UltiSnips

Useful snippets with [UltiSnips][ultisnips]:

* `try catch` statements.
* `for`, `foreach`, `while` loops.
* `if else` statements.
* `switch case` statements.
* `class`, `property`, `signal` definitions.
* many more!

## Additional functionality

* Set up to adhere to the [Vala Coding Style][vcs].
* A function to insert `CCode` attributes for the symbol below the cursor, useful when creating [Vala Legacy Bindings][vlb].

```vim
if has("autocmd")
	autocmd FileType vala ValaCodingStyle
	autocmd FileType vala noremap <F8> :CCode<CR>
end
```

[vala]:https://wiki.gnome.org/Projects/Vala
[vala-vim]:https://wiki.gnome.org/Projects/Vala/Vim
[vcs]:https://wiki.gnome.org/Projects/Vala/Hacking#Coding_Style
[vlb]:https://wiki.gnome.org/Projects/Vala/LegacyBindings
[ultisnips]:https://github.com/sirver/UltiSnips
