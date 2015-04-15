# Git Talk

Git is a pretty cool tool that enables developers to quickly and effectively
handle multiple versioning within a code base. The purpose of this talk is to
introduce the three aspects of changes within git.

## Building & Running 

Slides are written in markup and compiled into revealjs slides using a tool
called pandoc. You can easily get pandoc from your favorite package manager:

### Revealjs Dependency

Revealjs is added as a submodule so make sure you:
`git submodule init && git submodule update`

Also you must build the revealjs assets by: 

```
cd reveal.js
npm install .
grunt
```

### Build Slides

#### OS X (Homebrew)
`brew install pandoc`

#### Compiling Slides
`pandoc -t revealjs -s git-talk.md -o git-talk.html`


### View Slides

If you have python install you can use the http server module to server the
local directory.

#### Python2
`python -m SimpleHTTPServer`

#### Python3
`python -m http.server`
