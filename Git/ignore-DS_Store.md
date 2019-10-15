# Mac 系统下全局忽略.DS_Store 文件

- [参考](https://www.jianshu.com/p/8c0d262e49a6)

```
git config --global core.excludesfile ~/.gitignore
echo .DS_Store >> ~/.gitignore
```
