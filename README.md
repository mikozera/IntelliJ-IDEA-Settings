# JetBrains: Atom One Dark

![Project Image](https://lh3.googleusercontent.com/FD5qrsKPaVtgLAbrhbi-42YxWVaj_iEOyL4VJxTDdDYyY6OVadh9K-mrmKVBM2oooPqipriUthJ8zMNTHcP0Wsfdbjnzna1Fybl1=w1920-h997-rw-no)

> **IDE:** IntelliJ IDEA

---

## **Contents**

- [**Description**](#description)
  - [Features](#features)
- [**Installation**](#installation)
- [**Plugins**](#plugins)
  - [Mandatory](#mandatory)
  - [Recommended](#recommended)
- [**Bash Configuration**](#bash-configuration)
  - [Instructions](#instructions)
  - [Files](#files)
- [**Color Schemes**](#color-schemes)
  - [IntelliJ IDEA](#intellij-idea)
  - [WebStorm](#webstorm)
  - [PyCharm](#pycharm)
- [**License**](#license)
  - [MIT](#mit)
  
---

## **Description**
This is a FULL JetBrain's IDE configuration based off of Atom's One Dark theme. Apart from the theme, everything around the IDE has been set up to provide a beautiful and pleasant experience. 

### Features
- Atom One Dark Theme
- Fira Code Retina (w/ Font Ligatures)
- Optimized IDE Configuration
- Modified Keymap
- Improved GitBash Compatibility (w/ Bash Configuration)
- Awesome Plugins to Enhance the IDE Experience 
- Advanced Color Scheme Configuration for Most JetBrain's IDEs

> **Note:** Theme has been fully optimized for IntelliJ IDEA, WebStorm & PyCharm

---

## **Installation**
1. Download JetBrain's IDE
2. Install Plugins: File -> Settings -> Plugins -> Browse Repositories 
3. Install Bash Configuration
4. Enable Settings Repository: File -> Settings Repository -> Enter link: https://github.com/mikozera/JetBrains-Atom-One-Dark -> Override Local 

> **Note:** Theme comes with a adjusted Inspections Configuration & "optimized" Keymap

---

## **Plugins**

### Mandatory
- CodeGlance: enables a "Sublime-esk" mini-map
- Material Theme UI: enables a basic Atom One Dark theme
- Rainbow Brackets: enables colorful bracket/brace coloring

### Recommended
- .ignore: improved file ignoring capabilities
- AceJump: allows for quick cursor movement w/o taking your hands-off the keyboard (Ctrl + ;)
- Save Actions: auto-format your code 
- Markdown Navigator: integrates advanced Markdown support
- Presentation Assistant: displays any pressed keyboard shortcuts (Alt + Shift + D)

> **Note:** To enable auto-formatting, you must configure it under "Save Actions"

---

## **Bash Configuration**

### Instructions
1. Download Git for Windows (includes GitBash Terminal)
2. Locate or create ".bash_profile" and ".bashrc" files (C:\Users\\<user name\>)
3. Replace content within each of the files

### Files
##### .bash_profile
```bash
if [ -f ~/.bashrc ]; then
  source ~/.bashrc
fi
```

##### .bashrc
```bash
# Bash Configuration
PS1='\[\033]0;Terminal\007\]'
PS1="$PS1"'\[\033[32m\]' 
PS1="$PS1"'\u' 
PS1="$PS1"'\[\033[37m\]' 
PS1="$PS1"': ' 
PS1="$PS1"'\[\033[33m\]' 
PS1="$PS1"'\w' 

if test -z "$WINELOADERNOEXEC"
then
  GIT_EXEC_PATH="$(git --exec-path 2>/dev/null)"
  COMPLETION_PATH="${GIT_EXEC_PATH%/libexec/git-core}"
  COMPLETION_PATH="${COMPLETION_PATH%/lib/git-core}"
  COMPLETION_PATH="$COMPLETION_PATH/share/git/completion"
  if test -f "$COMPLETION_PATH/git-prompt.sh"
  then
    . "$COMPLETION_PATH/git-completion.bash"
    . "$COMPLETION_PATH/git-prompt.sh"
    PS1="$PS1"'\[\033[36m\]' 
    PS1="$PS1"'`__git_ps1`' 
  fi
fi
PS1="$PS1"'\[\033[37m\]' 
PS1="$PS1"'\n' 
PS1="$PS1"'$ ' 
```
---

## **Color Schemes**

### IntelliJ IDEA
> **Java** 
![Project Image](https://lh3.googleusercontent.com/yrB7yG9eB1xdNaPAssX5SrXL8OqEDh3aOQz_j19YJoZB9yxrQOY6qZc-3RCoZW6xkwQxOhfTt5fuAmZ_tE6YSxGupgZ1x-qaLPGBow=w1916-h995-rw-no)


### WebStorm
> **HTML**
![Project Image](https://lh3.googleusercontent.com/N5RPHtjH9sc40jJ0A3HpVa8I5uQP469z_G8hP5KkV7_ut4_RPwqUGWQSzlF1RfY90HT90-rOdzYY3232z-jXlu4Fog-vseiq_AMx=w1920-h994-rw-no)

> **CSS**
![Project Image](https://lh3.googleusercontent.com/lIJH4y4KICWwlc0UZkyJR_7FRkXHeBfKNKPkKSmB7yc7Ejsda6-ewWxB45oavDKV-TJat9Ja5HPq884zFyP_TzTOiepOoaSI9pcK=w1920-h996-rw-no)

> **SCSS** 
![Project Image](https://lh3.googleusercontent.com/p3Gp_AfnMzd5pLuaPArqy8KaWfxoJV_UCagL-WiYx6RjDwh3KC-ath4rDxMxaJs05yCIiCya-joV01Z4S_sQAhBbyc11S-YgBLxj=w1920-h998-rw-no)

> **JavaScript** 
![Project Image](https://lh3.googleusercontent.com/nPhlu7qn0KU0xLjD65S_uWn6xS1Fnh2fW3ehX81l2T_RYP3KwoCl6MV2rHY_p14w4UyfZH6gbWsVnIOhavOZ3XcurdiZHmlebZtb=w1920-h997-rw-no)


### PyCharm
> **Python**
![Project Image](https://lh3.googleusercontent.com/lj786HZSOreYF_J6bxXz0eguh0Y3yTR5oJ4sfKM766CFJlFHMX1c-qAEtmMJxK--wuZFLKgjWum6jhkTsH4KKNjdenA7N6EanxNj=w1920-h997-rw-no)
 

---
## **License**

### MIT

Copyright (c) 2019 Sebastian Nunez

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

[back to the top](#jetbrains-atom-one-dark)
