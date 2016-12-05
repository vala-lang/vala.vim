# vala.vim

- [Introduction](#introduction)
- [File detection](#file-detection)
- [Indentation](#indentation)
- [Syntax highlighting](#syntax-highlighting)
- [Snippets](#snippets)
- [Additional functionality](#additional-functionality)

## Introduction

vala.vim is a [Vim][vim] plugin that provides file detection, proper indentation, syntax highlighting and more for the [Vala programming language][vala].

The base version has been imported directly from the [official site][vala-vim].

Some of the improvements over the base version are listed below.

## File detection

Automatic detection of `.vala`, `.vapi` and `.valadoc` files.

## Indentation

The indentation file is largely based on the [rust.vim][rust-vim] plugin.
It is mainly a fix on top of `cindent` to:

* Method arguments.
* Attributes like `CCode`, `DBus`, etc.
* Lambda expressions, like those used inside a `foreach` method:

```vala
var list = new List<string> ();
list.append ("0. entry");
list.append ("1. entry");
list.append ("2. entry");
list.foreach ((entry) => {
	stdout.puts (entry);
	stdout.putc ('\n');
	if (entry == null) {
		stdout.printf ("null entry found\n");
	}
});
```

## Syntax highlighting

* Methods: any word followed by `(`.
* Arrays, lists and hash tables as in `Array<int>`, `List<string>` and `HashTable<string, int>`
* Operators and Delimiters: `+`, `-`, `*`, `/`, `=`, `( )`, `[ ]`, `{ }`...
* String formatting in `printf`-like methods: `%d`, `%f`, `%s`, `%c`, `%u`, `%%`...

## Snippets

Useful snippets with [UltiSnips][ultisnips]:

* `try catch` statements.
* `for`, `foreach`, `while` loops.
* `if else` statements.
* `switch case` statements.
* `class`, `property`, `signal` definitions.
* Documentation using [Valadoc][valadoc] taglets.
* many more!

## Additional functionality

This plugin comes with helper functions to:

* adhere to the [Vala Coding Style][vcs].
* insert `CCode` attributes for the symbol below the cursor, useful when creating [Vala Legacy Bindings][vlb].

Bind them by adding these lines to your `.vimrc`:

```vim
if has("autocmd")
	autocmd FileType vala ValaCodingStyle
	autocmd FileType vala noremap <F8> :CCode<CR>
end
```

[rust-vim]:https://github.com/rust-lang/rust.vim
[vala]:https://wiki.gnome.org/Projects/Vala
[vala-vim]:https://wiki.gnome.org/Projects/Vala/Vim
[valadoc]:https://valadoc.org
[vcs]:https://wiki.gnome.org/Projects/Vala/Hacking#Coding_Style
[vlb]:https://wiki.gnome.org/Projects/Vala/LegacyBindings
[vim]:http://www.vim.org/
[ultisnips]:https://github.com/sirver/UltiSnips
