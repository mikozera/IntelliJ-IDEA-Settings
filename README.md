# JetBrains: Atom One Dark

![Project Image](https://lh3.googleusercontent.com/mYzpNKYNA8o8xQqm7Ih1sQfPeRKi-Ns-4RGaB6bK-mwfRv2AbkOg7iBKr9WrB60ioB7vi5nhYeB-6i0j3TE0F1eRnTdsEy5wX2TjHw=w1867-h969-rw-no)

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
  - [PhpStorm](#phpstorm)
  - [CLion](#clion)
- [**License**](#license)
  - [MIT](#mit)
  
---

## **Description**
This is a complete JetBrain's IDE configuration based off of Atom's One Dark theme. Apart from the theme, everything around the IDE has been set up to provide a beautiful and pleasant experience. 

### Features
- Atom One Dark Theme
- Fira Code Retina (w/ Font Ligatures)
- Optimized IDE Configuration
- Modified Keymap
- Improved GitBash Compatibility (w/ Bash Configuration)
- Awesome Plugins to Enhance the IDE Experience 
- Advanced Color Scheme Configuration for Most JetBrain's IDEs

> **Note:** Theme has been fully optimized for IntelliJ IDEA, WebStorm, PyCharm, PhpStorm  & CLion

---

## **Installation**
1. Download JetBrain's IDE
2. Install Mandatory Plugins: File -> Settings -> Plugins -> Browse Repositories 
3. Install Bash Configuration
4. Enable Settings Repository: File -> Settings Repository -> Enter link: https://github.com/mikozera/JetBrains-Atom-One-Dark -> Override Local 

> **Note:** Must disable "Auto Sync" within the "Settings Repository"

---

## **Plugins**

### Mandatory
- Autoscroll Save: file tree is automatically expanded to the current file
- CodeGlance: enables a "Sublime-esk" mini-map
- Material Theme UI: enables a basic Atom One Dark theme
- Nyan Progress Bar: enables a colorful loading bar
- Rainbow Brackets: enables colorful bracket/brace coloring
- Save Actions: enables auto-formatting on save 
- Tabdir: enables improved editor tab support
- Path Hide: disables the default side-scrolling on the file tree

> **Note:** To enable auto-formatting, you must configure it under "Save Actions"

### Recommended
- .ignore: improved file ignoring capabilities
- Bootstrap 4: allows for advanced Bootstrap 4 snippets
- Import Cost: calculates file sizes for dependencies
- Markdown Navigator: integrates advanced Markdown support
- React Snippets: enhances React support
- React PropTypes: enhances React PropType validation via a UI (Alt + Ins)
- String Manipulation: allows for smart string manipulation (Alt + Shift + M)
- Presentation Assistant: displays any pressed keyboard shortcuts (Alt + Shift + D)

> **Note:** When adding new plugins make sure to "update" the IDE by repeating "Step 4" of the "Installation"

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
if [[ $COLORTERM = gnome-* && $TERM = xterm ]] && infocmp gnome-256color >/dev/null 2>&1; then
	export TERM='gnome-256color';
elif infocmp xterm-256color >/dev/null 2>&1; then
	export TERM='xterm-256color';
fi;

prompt_git() {
	local s='';
	local branchName='';

	git rev-parse --is-inside-work-tree &>/dev/null || return;

	branchName="$(git symbolic-ref --quiet --short HEAD 2> /dev/null || \
		git describe --all --exact-match HEAD 2> /dev/null || \
		git rev-parse --short HEAD 2> /dev/null || \
		echo '(unknown)')";

	repoUrl="$(git config --get remote.origin.url)";
	if grep -q 'chromium/src.git' <<< "${repoUrl}"; then
		s+='*';
	else

		if ! $(git diff --quiet --ignore-submodules --cached); then
			s+='+';
		fi;

		if ! $(git diff-files --quiet --ignore-submodules --); then
			s+='!';
		fi;

		if [ -n "$(git ls-files --others --exclude-standard)" ]; then
			s+='?';
		fi;

		if $(git rev-parse --verify refs/stash &>/dev/null); then
			s+='$';
		fi;
	fi;

	[ -n "${s}" ] && s=" [${s}]";

	echo -e "${1}${branchName}${2}${s}";
}

if tput setaf 1 &> /dev/null; then
	tput sgr0;
	bold=$(tput bold);
	reset=$(tput sgr0);
	black=$(tput setaf 0);
	blue=$(tput setaf 39);
	cyan=$(tput setaf 37);
	green=$(tput setaf 40);
	orange=$(tput setaf 202);
	purple=$(tput setaf 125);
	red=$(tput setaf 196);
	violet=$(tput setaf 129);
	white=$(tput setaf 15);
	yellow=$(tput setaf 226);
else
	bold='';
	reset="\e[0m";
	black="\e[1;30m";
	blue="\e[1;34m";
	cyan="\e[1;36m";
	green="\e[1;32m";
	orange="\e[1;33m";
	purple="\e[1;35m";
	red="\e[1;31m";
	violet="\e[1;35m";
	white="\e[1;37m";
	yellow="\e[1;33m";
fi;

if [[ "${USER}" == "root" ]]; then
	userStyle="${red}";
else
	userStyle="${green}";
fi;

if [[ "${SSH_TTY}" ]]; then
	hostStyle="${red}";
else
	hostStyle="${orange}";
fi;

PS1="\[\033]0;\W\007\]";
PS1+="\[${userStyle}\]\u";
PS1+="\[${white}\] at ";
PS1+="\[${hostStyle}\]\h";
PS1+="\[${white}\] in ";
PS1+="\[${yellow}\]\W";
PS1+="\$(prompt_git \"\[${white}\] on \[${blue}\]\" \"\[${violet}\]\")";
PS1+="\n";
PS1+="\[${white}\]\$ \[${reset}\]"; s
export PS1;

PS2="\[${yellow}\]→ \[${reset}\]";
export PS2;

```
---

## **Color Schemes**

### IntelliJ IDEA
> **Java** 
![IntelliJ IDEA - Java](https://lh3.googleusercontent.com/tmuriilklF0aD6bPOkxEBGEa8ii2JCjBetBMW-0a91wcYiSLH_fsfBsdM8M76h8f2Xa6ltSyh9fZ0A=w1866-h969-rw-no)


### WebStorm
> **HTML**
![WebStorm - HTML](https://lh3.googleusercontent.com/CbbAhtR4n-S1wMweHfyKHe06vv9cTJx32zI0HUW5apbqByVLawxHyFsJt6gj6Rb0FRCuB_JM05rLXF39j1IM3dFOFVj7YOBRjL5V=w1872-h969-rw-no)

> **CSS**
![WebStorm - CSS](https://lh3.googleusercontent.com/12Z-HSwgx1tKG8TV9cGaiVnQPG_CRt7zk7uk9GT93r6pD9IIJ6kVECHbXfUpWNXUMhPUSGSpQzQsGS3h4vEs86QB8QdzqvvJY6sX=w1868-h969-rw-no)

> **SCSS** 
![WebStorm - SCSS](https://lh3.googleusercontent.com/eqPWMnVP99z7PoSPNoFz9XgwwL38kQBfH06mcgD1uYpDrjZ9xSVMhBnRIaxxYHqPE-y4sETQW6MXnhuWK7tbdF4ROVh_aSxLOXlU=w1867-h969-rw-no)

> **JavaScript** 
![WebStorm - JavaScript](https://lh3.googleusercontent.com/vJBKtFMuFgzfMR0EBwJpuwgBm6SY5MYW_BA-cCXAI2c3rA6IJrPRazXwHtNgjEDboqUUVLrDy5BKO6rNe_9BH-I-Lv1oX5xDPY-l=w1870-h969-rw-no)

### PyCharm
> **Python**
![PyCharm - Python](https://lh3.googleusercontent.com/6KALxyKTrtqEZGJf4-7YIeFV9WOaxZSct7rOGMggKjmyeXwNpCWuzX68dBernUcA75cAFHC8S5rZQg=w1868-h969-rw-no)

### PhpStorm
> **PHP**
![PhpStorm - PHP](https://lh3.googleusercontent.com/KLOKE9UOKNVTEPIwsDAV9IOmLFDGL4wx17H1E8ixlCnGy82a3H75NMlNBVxIX03grhhDW8G6RzrY2Q=w1874-h969-rw-no)

### CLion
> **C**
![Project Image](https://lh3.googleusercontent.com/cF8iBfkXUrR0aSGDVxDFZgo0I3z6sTGC2pAIcUVr6bDS_hQuE_Ay4QjnhaaOGQCvm41rAf6JF69QEhsrusFQkFeL9IEboQUhwL4bIQ=w1868-h969-rw-no)

> **C++**
![Project Image](https://lh3.googleusercontent.com/K5kkt-YaZV5QStjbVdIiR9MXB6SaYyFObd0LuP0b4JglGhFAuJ64WcF0Tdctl2EAAU9EaMEyoQ978A=w1867-h969-rw-no)
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
