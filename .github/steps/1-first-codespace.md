<!--
  <<< Author notes: Step 1 >>>
  Choose 3-5 steps for your course.
  The first step is always the hardest, so pick something easy!
  Link to docs.github.com for further explanations.
  Encourage users to open new tabs for steps!
-->

## Step 1: 创建你的第一个 Codespace 并推送代码

_欢迎来到课程《使用 GitHub Codespaces 和 Visual Studio Code 开发代码》! :wave:_

**为什么要用 Codespace 来开发软件？**
Codespace 是一个托管在云端的开发环境。你可以通过将配置文件提交到仓库中（这也叫 “配置即代码” 的方式）来配置开发环境，这样一来，保证了所有开发者都能在统一、可重复的环境中高效工作。

每一个 Codespace 都运行在 GitHub 提供的虚拟机上，由 Docker 容器托管。你可以根据项目所需资源选择不同类型的虚拟机。

GitHub 提供了一系列功能，帮助你的团队灵活定制 Codespace，以实现最佳的开发体验与性能表现。例如，你可以：

- 直接从仓库创建一个 Codespace
- 从 Codespace 中推送代码到仓库
- 使用 VS Code 进行开发
- 通过自定义镜像调整环境
- 管理你的 Codespace

要开始使用 GitHub Codespaces 进行开发，你可以基于模板创建一个 Codespace，也可以从仓库中的任意分支或commit启动。
当你从模板创建时，可以选择空白模板，或使用适合你当前开发任务的预设模板。

### :keyboard: 实操环节: 启动一个 Codespace

**建议你在浏览器中新开一个标签页进行以下操作，方便一边动手实践一边阅读本教程。**

1. 打开你的仓库主页。
2. 点击页面中间的绿色 **Code** 按钮。
3. 在弹出的窗口中，切换到 **Codespaces** 标签页，然后点击 **Create codespace on main** 按钮。
   > 等待大约 2 分钟，Codespace 会在后台自动启动。
   > **提示**：这是一个虚拟机启动的过程。
4. 确认 Codespace 是否成功运行。浏览器中会打开一个基于 Web 的 VS Code 编辑器，同时底部会显示终端窗口，如下图所示：
   ![codespace1](https://user-images.githubusercontent.com/26442605/207355196-71aab43f-35a9-495b-bcfe-bf3773c2f1b3.png)


### :keyboard: 实操环节：从 Codespace 推送代码到仓库

1. 在 Codespace 中，打开 VS Code 左侧资源管理器，找到并选择 `index.html` 文件。
2. 将文件中的 **h1** 标签替换为以下内容：
   ```html
   <h1>Hello from the codespace!</h1>
   ```
3. 保存文件。
   > **提示**：VS Code 通常会自动保存文件。
4. 在 VS Code 的终端中输入以下命令提交更改：
   ```shell
   git commit -a -m "Adding hello from the codespace!"
   ```
5. 将更改推送回仓库：
   ```shell
   git push
   ```
6. 现在你的代码已经成功推送到 GitHub 仓库！
7. 回到仓库主页，打开 `index.html` 文件，确认修改是否已经更新到仓库中。
8. 等待大约 20 秒后刷新当前页面。[GitHub Actions](https://docs.github.com/en/actions) 会自动检测你的进度并跳转到下一步。