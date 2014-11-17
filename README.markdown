# boot.vim

Static Vim support for [Boot][].

* `:Console` command to start a REPL or focus an existing instance if already
  running using [dispatch.vim][].
* Autoconnect [fireplace.vim][] to the REPL, or autostart it with `:Console`.
* [Navigation commands][projectionist.vim]: `:Esource`, `:Emain`, `:Etest`,
  and `:Eresource`.
* Alternate between test and implementation with `:A`.
* Use `:make` to invoke `lein`, complete with stacktrace parsing.
* Default [dispatch.vim][]'s `:Dispatch` to running the associated test file.
* `'path'` is seeded with the classpath to enable certain static Vim and
  [fireplace.vim][] behaviors.

[Boot]: https://github.com/boot-clj/boot
[fireplace.vim]: https://github.com/tpope/vim-fireplace
[dispatch.vim]: https://github.com/tpope/vim-dispatch
[projectionist.vim]: https://github.com/tpope/vim-projectionist

## Installation

If you don't have a preferred installation method, I recommend
[NeoBundle](https://github.com/Shougo/neobundle.vim).

```vim
" In your .vimrc
NeoBundle 'rkneufeld/vim-boot'
```

Others prefer [pathogen.vim](https://github.com/tpope/vim-pathogen). To
install, simply copy and paste:

    cd ~/.vim/bundle
    git clone git://github.com/rkneufeld/vim-boot.git
    git clone git://github.com/tpope/vim-projectionist.git
    git clone git://github.com/tpope/vim-dispatch.git
    git clone git://github.com/tpope/vim-fireplace.git

Once help tags have been generated, you can view the manual with
`:help boot`.

## FAQ

> Why does it sometimes take a few extra seconds for Vim to startup?

Much of the functionality of leiningen.vim depends on knowing the classpath.
When possible, this is retrieved from a [fireplace.vim][] connection, but if
not, this means a call to `boot classpath`.

You should add the following task to your build.boot:

```clojure
;; ...
```

Once retrieved, the classpath is cached until `boot.build` changes.

## License

Copyright © Ryan Neufeld.  Distributed under the same terms as Vim itself.
See `:help license`.

Special thanks to [@tpope](https://github.com/tpope) for creating the original
[vim-leiningen](https://github.com/tpope/vim-leiningen), upon which this plugin
is based.

