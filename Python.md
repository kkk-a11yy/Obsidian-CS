# 安装
- 通过home-brew
	- [pyenv/pyenv: Simple Python version management](https://github.com/pyenv/pyenv#homebrew-in-macos)
```r
brew update
brew install pyenv

echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.zshrc
```
