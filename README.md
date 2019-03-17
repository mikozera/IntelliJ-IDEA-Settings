# JetBrains: Atom One Dark

![Project Image](https://lh3.googleusercontent.com/mYzpNKYNA8o8xQqm7Ih1sQfPeRKi-Ns-4RGaB6bK-mwfRv2AbkOg7iBKr9WrB60ioB7vi5nhYeB-6i0j3TE0F1eRnTdsEy5wX2TjHw=w1920-h997-rw-no)

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
2. Locate or create ".bash_profile" and ".bashrc" files (C:\Users\<your user name>)
3. Replace content within each of the files

### Files
##### .bash_profile
```
if [ -f ~/.bashrc ]; then
  source ~/.bashrc
fi
```

##### .bashrc
```
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
![Project Image](https://lh3.googleusercontent.com/xWdaGJHma7FRaSa48R1FVIOoHK0EEFd6lwtyfbql4guaSDZRqDYDZk3myovVtHQxuKUlCWw_FM95aaSpsQYn65k2nGf0-zC5KGGm4g=w1920-h997-rw-no)


### WebStorm
> **HTML**
![Project Image](https://lh3.googleusercontent.com/CbbAhtR4n-S1wMweHfyKHe06vv9cTJx32zI0HUW5apbqByVLawxHyFsJt6gj6Rb0FRCuB_JM05rLXF39j1IM3dFOFVj7YOBRjL5V=w1920-h994-rw-no)

> **CSS**
![Project Image](https://lh3.googleusercontent.com/12Z-HSwgx1tKG8TV9cGaiVnQPG_CRt7zk7uk9GT93r6pD9IIJ6kVECHbXfUpWNXUMhPUSGSpQzQsGS3h4vEs86QB8QdzqvvJY6sX=w1920-h996-rw-no)

> **SCSS** 
![Project Image](https://lh3.googleusercontent.com/eqPWMnVP99z7PoSPNoFz9XgwwL38kQBfH06mcgD1uYpDrjZ9xSVMhBnRIaxxYHqPE-y4sETQW6MXnhuWK7tbdF4ROVh_aSxLOXlU=w1920-h997-rw-no)

> **JavaScript** 
![Project Image](https://lh3.googleusercontent.com/vJBKtFMuFgzfMR0EBwJpuwgBm6SY5MYW_BA-cCXAI2c3rA6IJrPRazXwHtNgjEDboqUUVLrDy5BKO6rNe_9BH-I-Lv1oX5xDPY-l=w1920-h995-rw-no)


### PyCharm
> **Python**
![Project Image](https://lh3.googleusercontent.com/cFKi866G55a_KfCXwGDgobcjBhLvQ3Q2tTTX1MhKp5MNw-yEvdjiZRTeTFOF-Q0P5eucfAzPeWxAajiAyAiC3cfHp4RkXForY9-I=w1920-h996-rw-no)
 

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
