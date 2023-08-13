# 安装
## 通过home-brew安装pyenv
- 安装资料： [pyenv/pyenv: Simple Python version management](https://github.com/pyenv/pyenv#homebrew-in-maco
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
    [](https://github.com/pyenv/pyenv/wiki#pyenv-is-installed-but-things-just-arent-working-for-me)

- home-brew安装路径：[Homebrew](Configuration/homebrew/Homebrew.md#^b49b8b)

