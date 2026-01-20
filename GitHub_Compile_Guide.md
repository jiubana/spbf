# 上传并编译 "扣货科技" (QMPlay2) 指南

自动上传到您的仓库失败（通常是因为需要 GitHub 账号密码验证）。请按照以下步骤在您的电脑上手动完成上传。

## 第一步：手动上传代码

打开您的终端（PowerShell），复制并执行以下命令：

```powershell
cd "c:\Users\ADMIN\Desktop\快播\QMPlay2-Source"

# 1. 确认远程仓库地址（我已经帮您设置好了，但为了保险请检查）
git remote set-url origin https://github.com/jiubana/khkj.git

# 2. 推送代码
# 执行这一步时，弹窗可能会要求您输入 GitHub 账号和密码（或 Token）
git push -u origin master --force
```

## 第二步：解决无法编译的问题（重要！）

由于我们无法从官方仓库自动获取编译脚本（`.github` 文件夹），通过上述方式上传的代码 **无法自动触发编译**。

**推荐的解决方案：**

1.  请不要使用 `jiubana/khkj` 空仓库。
2.  **直接在 GitHub 上 Fork 官方仓库**：[https://github.com/zaps166/QMPlay2](https://github.com/zaps166/QMPlay2)
3.  Fork 完成后，您会得到一个类似 `https://github.com/jiubana/QMPlay2` 的仓库，里面已经包含了所有编译脚本。
4.  然后，将通过第一步上传到 `khkj` 的以下修改过的文件，**手动复制**或**上传**到您的新 Fork 仓库中：
    *   `src/gui/Main.cpp`
    *   `src/gui/AboutWidget.cpp`
    *   `src/gui/Updater.cpp`
    *   `src/gui/MenuBar.cpp`
    *   `src/gui/MainWidget.cpp`
    *   `src/gui/resources.qrc`
    *   `src/qmplay2/InDockW.cpp`
    *   `src/gui/background.jpg`

这样做最简单，因为编译环境配置非常复杂，官方仓库已经为您配置好了。
