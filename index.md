---
layout: index
---

CopyQ is advanced clipboard manager with editing and scripting features.

## Links

- [Downloads](https://github.com/hluk/CopyQ/releases)
- [Documentation](https://copyq.readthedocs.io)
- [Mailing List](https://groups.google.com/group/copyq)
- [Bug Reports](https://github.com/hluk/CopyQ/issues)
- [Donate](https://www.bountysource.com/teams/copyq)
- [Scripting API](https://copyq.readthedocs.io/en/latest/scripting-api.html)

## Overview

CopyQ monitors system clipboard and saves its content in customized tabs.
Saved clipboard can be later copied and pasted directly into any application.

Items can be:

* edited with internal editor or with preferred text editor,
* moved to other tabs,
* drag'n'dropped to applications,
* marked with tag or a note,
* passed to or changed by custom commands,
* or simply removed.

## Screenshots

![Preview](images/application.png)
![Items](images/screenshot-items.png)
![Simple Editor](images/screenshot-editor.png)
![Tabs](images/screenshot-tabs.png)
![Tree View](images/screenshot-tree.png)
![Run Action and Create Items](images/screenshot-action.png)
![Open in Web Browser](images/screenshot-browser.png)

## Features

* Support for Linux, Windows and OS X 10.9+
* Store text, HTML, images or any other custom formats
* Quickly browse and filter items in clipboard history
* Sort, create, edit, remove, copy/paste, drag'n'drop items in tabs
* Add notes or tags to items
* System-wide shortcuts with customizable commands
* Paste items with shortcut or from tray or main window
* Fully customizable appearance
* Advanced command-line interface and scripting
* Ignore clipboard copied from some windows or containing some text
* Support for simple Vim-like editor and shortcuts
* Many more features

## Install and Run

To install CopyQ, use the binary package or installer provided for your system. For system-specific information, please see below. For unlisted systems, please follow the instructions in
[INSTALL](https://github.com/hluk/CopyQ/blob/master/INSTALL) to build the
application.

### Windows

On Windows you can install [Chocolatey package](https://chocolatey.org/packages/copyq).

### Ubuntu

Install and keep CopyQ always up to date by running the following three commands from the terminal:

```bash
$ sudo add-apt-repository ppa:hluk/copyq
$ sudo apt update
$ sudo apt install copyq
```

### OS X

On OS X you can use [Homebrew](https://brew.sh/) to install the app.

```bash
brew cask install copyq
```

## Using the App

To start the application double-click the program icon or run `copyq`.

The list with clipboard history is accessible by clicking on system tray icon
or running `copyq toggle`.

Copying text or image to clipboard will create new item in the list.

Selected items can be:
* edited (`F2`),
* removed (`Delete`),
* sorted (`Ctrl+Shift+S`, `Ctrl+Shift+R`),
* moved around (with mouse or `Ctrl+Up/Down`) or
* copied back to clipboard (`Enter`, `Ctrl+V`).

All items will be restored when application is started next time.

To exit the application select Exit from tray menu or press Ctrl-Q keys in the
application window.

Read more:
- [Basic Usage](https://copyq.readthedocs.io/en/latest/basic-usage.html)
- [Keyboard](https://copyq.readthedocs.io/en/latest/keyboard.html)

### Adding Funcionality

To create custom action that can be executed
from menu, with shortcut or when clipboard changes:
- go to Command dialog (`F6` shortcut),
- click Add button and select predefined command or create new one,
- optionally change the command details (shortcut, name),
- click OK to save the command.

One of very useful predefined commands there is "Show/hide main window".

Read more:
- [Writing Commands](https://copyq.readthedocs.io/en/latest/writing-commands-and-adding-functionality.html)
- [CopyQ Commands Repository](https://github.com/hluk/copyq-commands)

### Command Line

CopyQ has powerful command line and scripting interface.

Note: The main application must be running to be able to issue commands using
command line.

Print help for some useful command line arguments:

    copyq --help
    copyq --help add

Insert some texts to the history:

    copyq add "first item" "second item" "third item"

Print content of the first three items:

    copyq read 0 1 2
    copyq separator "," read 0 1 2

Show current clipboard content:

    copyq clipboard
    copyq clipboard text/html
    copyq clipboard \?    # lists formats in clipboard

Copy text to the clipboard:

    copyq copy "Some Text"

Load file content into clipboard:

    copyq copy - < file.txt
    copyq copy text/html < index.html
    copyq copy image/jpeg - < image.jpg

Create an image items:

    copyq write image/gif - < image.gif
    copyq write image/svg - < image.svg

Read more:
- [Scripting](https://copyq.readthedocs.io/en/latest/scripting.html)
- [Scripting API](https://copyq.readthedocs.io/en/latest/scripting-api.html)

## Build from Source Code

To build the application from source code, first install the required dependencies:
- [Git](https://git-scm.com/)
- [CMake](https://cmake.org/download/)
- [Qt](https://download.qt.io/archive/qt/)
- Optionally on Linux/X11: development files and libraries for [Xtst](https://t2-project.org/packages/libxtst.html) and [Xfixes](https://www.x.org/archive/X11R7.5/doc/man/man3/Xfixes.3.html)
- Optionally [QtWebKit](https://trac.webkit.org/wiki/QtWebKit) (more advanced HTML rendering)

### Ubuntu

#### Install Dependencies

```bash
sudo apt install \
  git cmake \
  qtbase5-private-dev \
  qtscript5-dev \
  qttools5-dev \
  qttools5-dev-tools \
  libqt5svg5-dev \
  libxfixes-dev \
  libxtst-dev \
  libqt5svg5
```

#### Build the App

Change install prefix if needed:

```bash
git clone https://github.com/hluk/CopyQ.git
cd CopyQ
cmake -DCMAKE_INSTALL_PREFIX=/usr/local .
make
```

#### Install the App

```bash
sudo make install
```

## Contributions

You can help translate the application (click the banner below)
or help [fix issues and implement new features](https://github.com/hluk/CopyQ/issues).

[![Translations](https://hosted.weblate.org/widgets/copyq/-/287x66-white.png)](https://hosted.weblate.org/engage/copyq/?utm_source=widget)

Read more:
- [Build from Source Code](https://copyq.readthedocs.io/en/latest/build-source-code.html)
- [Fixing Bugs and Adding Features](https://copyq.readthedocs.io/en/latest/fixing-bugs.html)
See also [Development](https://github.com/hluk/CopyQ/wiki/Development).