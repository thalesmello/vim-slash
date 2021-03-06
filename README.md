vim-slash
=========

vim-slasher (fork of [vim-slash][vim-slash]) provides a set of mappings for enhancing
in-buffer search experience in Vim.

- Automatically clears search highlight when cursor is moved
- Improved-star motion: hit once to highlight, repeat to jump next
- Improved visual star-motion: hit once in visual mode to highlight, repeat to
  move to next highlighted term
- Enhanced `cgn` substitution: highlight only disappears when you move cursor
  in normal mode, so that you easily see when repeated operations are going to
  act.
- Indexed search message, borrowed from [vim-indexed-search].

Installation
------------

Using [vim-plug](https://github.com/junegunn/vim-plug):

```vim
Plug 'thalesmello/vim-slasher'
```

Comparison with vim-slash
---------------------------

vim-slasher is a fork of [vim-slash][vim-slash] [with additional features rejected by the original author][rejected-features].

It provides:

- Search movement by repeating the star key
- Omits the search text in the status message
- Highlight doens't disappear when changing text (for `cgn` substitution)
- Indexed search message, from [vim-indexed-search].

Customization
-------------

#### `zz` after search

Places the current match at the center of the window.

```vim
noremap <plug>(slash-after) zz
```

#### Blinking cursor after search using Vim 8 timer

```vim
if has('timers')
  " Blink 2 times with 50ms interval
  noremap <expr> <plug>(slash-after) slasher#blink(2, 50)
endif
```

You can prepend `zz` to the expression: `'zz'.slasher#blink(2, 50)`

Thanks
------

This plugin is based on the amazing work by [Junegunn Choi](https://github.com/junegunn), which brought us
[vim-slash][vim-slash], [vim-plug][vim-plug] and the amazing [fzf][fzf].

The indexed search was only possible because of the work of [Iener Yakov][iener], [Otto Modinos][otto] and [Hendrik Nyh][hendrik] in [vim-indexed-search][vim-indexed-search].

I wanted to combine features of both plugins, plus a few extras, so it motivated me to build this one.

[vim-slash]: https://github.com/junegunn/vim-slash
[rejected-features]: https://github.com/junegunn/vim-slash/pull/
[vim-plug]: https://github.com/junegunn/vim-plug
[fzf]: https://github.com/junegunn/fzf
[otto]: https://github.com/otommod
[iener]: https://vim.sourceforge.io/account/profile.php?user_id=2342
[hendrik]: https://github.com/henrik/
[vim-indexed-search]: https://github.com/henrik/vim-indexed-search

