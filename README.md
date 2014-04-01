# Nonlocal Spin Valve in TikZ

**Copyright 2014 Evan Sosenko**

## Requirements

- `xelatex` and [`la­texmk`](http://www.ctan.org/pkg/latexmk/)
  packaged with a modern LaTeX distribution,
  e.g., [TeX Live](http://www.tug.org/texlive/).
- [Ruby 2](https://www.ruby-lang.org/)
  with [Bundler](http://bundler.io/) (optional).

## Including in a TeX document

You can add this to you project as [bower](http://bower.io/)
package using a git endpoint.

Alternatively, add any files in the `tex` directory
that begin with an underscore to your project.

Once the files are available under your project root,
include the tex files with `\input`:

  - `_packages.tex` should be included in your preamble.
  - `_nonlocal_spin_valve.tex` should be included
    wherever you want to include the picture as follows:

````latex
\input{_head}
\begin{tikzpicture}
  \input{_nonlocal_spin_valve}
\end{tikzpicture}
````

## Building

### With Ruby

If you have Ruby with Bundler, install the needed gems with

````bash
$ bundle
````

To build all targets,

````bash
$ rake
````

Output files will be saved in the `build` directory.

To see other rake tasks,

````bash
$ rake -D
````

You can run

````bash
$ guard
````

which will automatically rebuild on changes.

### Without Ruby

To build the tex source,

````bash
$ cd tex
$ latexmk -xelatex nonlocal_spin_valve.tex
````

## License

This work is Copyright 2014 Evan Sosenko.

## Warranty

This software is provided "as is" and without any express or
implied warranties, including, without limitation, the implied
warranties of merchantibility and fitness for a particular
purpose.
