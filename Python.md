# 安装
## 通过home-brew安装pyenv
- 安装资料： [pyenv/pyenv: Simple Python version management](https://github.com/pyenv/pyenv#homebrew-in-maco
- 使用代码：
```r
brew update
brew install pyenv

echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.zshrc
```
- home-brew安装路径：[Homebrew](Configuration/homebrew/Homebrew.md#^b49b8b)
- [[Configuration/homebrew/Homebrew.md^|Homebrew]]
