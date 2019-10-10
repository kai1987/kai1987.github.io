---
title: Migrate from Vim to VSCode
date: 2019-10-04 00:12:34
tags: Vim,VSCode
---

## First Why?

1. I joined a new company and I have to use Windows duraing work, the Vim in windows is not easy to use, so I decide to Migrate to VSCode.
1. VSCode is more friend to JavaScript which I'm using now.
1. VSCode has lots of extensions.

## VSCODE Extensions you need.
1. Vim
1. ESLint

## Tools that may help

1. [Chocolatey](https://chocolatey.org/) The package manager for windows, like brew on macOS and apt or yum on linux.

1. [Cmder](https://cmder.net/) A Portable console emulator for Windows.

1. Use Cmder as default terminal on VSCode. See <https://github.com/cmderdev/cmder/wiki/Seamless-VS-Code-Integration>

## Vim extensions configs for me.

set "jj" to back to normal mode. 

<https://github.com/VSCodeVim/Vim>


## Trobules fixed.
1. Powershell and Cmder can't use the c:\Users\[YourUser]\.ssh, 
Solution: copy .ssh to c:\Users\[YourUser]\.config\


## IME
SouGou English auto complete, when you are in Chinese mode. then use "shift + control + E" you can change to English mode with auto complete. so no worry for the vocabulary you can't spell.




