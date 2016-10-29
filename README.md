# vala.vim

This is a Vim plugin that provides [Vala][vala] file detection, syntax highlighting and more.

`vala.vim` is contains a Vim syntax, indent and ftdetect files for Vala.

The base version has been imported directly from the [official site][vala-vim].

It improves the syntax highlighting:

* Methods ()
* Arrays, lists and hash tables as in `Array<int>`, `List<string>` and `HashTable<string, int>`
* Operators and Delimiters
* Formatting characters in `printf`-like methods

It also adds useful snippets using [UltiSnips][ultisnips].

## Additional configuration for Vala files

In order to adhere to the official [Vala Coding Style][vcs], a few commands should be placed inside your `.vimrc`:

```vim
if has("autocmd")
	autocmd FileType vala setlocal ts=4 sts=4 sw=4 tw=200
endif

" Mapping to ease the creation of CCode in vapi files
noremap <F8> "gyiwO[CCode (cname = "<ESC>"gpa")]<ESC>
```

See [Vala Legacy Bindings][ccode] for the mapping.

[vala]:https://wiki.gnome.org/Projects/Vala
[vala-vim]:https://wiki.gnome.org/Projects/Vala/Vim
[vcs]:https://wiki.gnome.org/Projects/Vala/Hacking#Coding_Style
[ccode]:https://wiki.gnome.org/Projects/Vala/LegacyBindings
[ultisnips]:https://github.com/sirver/UltiSnips
