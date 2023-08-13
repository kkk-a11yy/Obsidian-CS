# 安装
## 通过home-brew安装pyenv
- 安装资料：
	- [pyenv/pyenv: Simple Python version management](https://github.com/pyenv/pyenv#set-up-your-shell-environment-for-pyenv)
	- [pyenv/COMMANDS.md at master · pyenv/pyenv](https://github.com/pyenv/pyenv/blob/master/COMMANDS.md#pyenv-install)
	- [Home · pyenv/pyenv Wiki](https://github.com/pyenv/pyenv/wiki#suggested-build-environment)
	- [Python Releases for macOS | Python.org](https://www.python.org/downloads/macos/)
- 使用代码：
```r
brew update
brew install pyenv

### Set up your shell environment for Pyenv
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.zshrc

alias brew='env PATH="${PATH//$(pyenv root)\/shims:/}" brew'

### Restart your shell
exec "$SHELL"

### Install Python build dependencies
  ### Suggested build environment
     **Mac OS X:**
 brew install openssl readline sqlite3 xz zlib tcl-tk

```

```r
###Check that pyenv is in your PATH:

which pyenv

###Check that pyenv's shims directory is in your PATH:

echo $PATH | grep --color=auto "$(pyenv root)/shims"

```
1. If not, see [Configure your shell's environment for pyenv](https://github.com/pyenv/pyenv/#basic-github-checkout) in the installation instructions.
    [pyenv-is-installed-but-things-just-arent-working-for-me](https://github.com/pyenv/pyenv/wiki#pyenv-is-installed-but-things-just-arent-working-for-me)

```r
不同的 Unix-like shell（命令行解释器）中，应该将 pyenv 的配置放在哪个启动文件
Which shell startup file do I put pyenv config in?

Typically it's one of the following:

bash: ~/.bash_profile
zsh: ~/.zshrc
ksh: ~/.kshrc
other: ~/.profile
```
## pyenv安装python3.11.4
```r
pyenv install -l
pyenv install 3.11.4

Installed Python-3.11.4 to /Users/ksia/.pyenv/versions/3.11.4
```
## 选择python版本作为全局配置
```r
pyenv global 3.11.4
```
## 卸载python版本
```r
pyenv uninstall <version>
```
## 查看pyenv commands
```r
 pyenv commands
```
## 查看目前安装的python版本
```r
ksia@bogon ~ % pyenv version 
3.11.4 (set by /Users/ksia/.pyenv/version)
```


- home-brew安装路径：[Homebrew](Configuration/homebrew/Homebrew.md#^b49b8b)

