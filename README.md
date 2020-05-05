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

##### .bashrc (Windows)
```
# Bash Configuration (Windows)
PS1='\[\033]0;Terminal\007\]'
PS1="$PS1"'\[\033[32m\]'
PS1="$PS1"'\u'
PS1="$PS1"'\[\033[37m\]'
PS1="$PS1"': '
PS1="$PS1"'\[\033[33m\]'
PS1="$PS1"'\W'

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

##### .bashrc (macOS)
```
# Bash Configuration (macOS)
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

	echo -e "${1}${branchName}${2}";
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
PS1+="\[${white}\]: ";
PS1+="\[${yellow}\]\W";
PS1+="\$(prompt_git \"\[${white}\] \[${blue}\](\" \")\")";
PS1+="\n";
PS1+="\[${white}\]\$ \[${reset}\]";
export PS1;

PS2="\[${yellow}\]→ \[${reset}\]";
export PS2;

```

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
