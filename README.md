<header>

<!--
  <<< Author notes: Course header >>>
  Read <https://skills.github.com/quickstart> for more information about how to build courses using this template.
  Include a 1280×640 image, course name in sentence case, and a concise description in emphasis.
  In your repository settings: enable template repository, add your 1280×640 social image, auto delete head branches.
  Next to "About", add description & tags; disable releases, packages, & environments.
  Add your open source license, GitHub uses the MIT license.
-->

[English](https://github.com/skills/code-with-codespaces) | 中文

> 本课程翻译自 Github Skills，全部课程请点击 [这里查看](https://www.github-zh.com/getting-started)

# 使用 GitHub Codespaces 和 Visual Studio Code 编写代码

_在云端使用 GitHub Codespaces 和 Visual Studio Code 编写代码_

</header>

<!--
  <<< Author notes: Step 4 >>>
  Start this step by acknowledging the previous step.
  Define terms and link to docs.github.com.
-->

## Step 4: 个性化你的 Codespace!

_很棒!你已经完成了 Codespace 的基础设置!_ :partying_face:

工欲善其事，必先利其器。无论是使用本地还是云端开发环境，按照自己的喜好和工作流来调整设置与工具，是提升开发效率的重要一步。
GitHub Codespaces 提供了两种主要的个性化方式：使用 VS Code 的 **Settings Sync（设置同步）**，以及使用 **dotfiles（点文件）**。

在本节中，我们将重点学习 **dotfiles**。

**什么是 `dotfiles`?** 它是一类在 Unix-like 系统中以 `.` 开头的文件或文件夹，用于控制系统上应用程序和 shell 的配置。
你可以在 GitHub 上创建一个仓库存放并管理这些 dotfiles，这样每次创建新的 Codespace 时，都能自动加载你喜欢的配置。

下面我们具体演示下!

### :keyboard: 实操环节: 启用 `dotfile`

1. 进入仓库主页。
2. 点击右上角的个人头像，选择 **Settings（设置）**。
3. 在左侧边栏的 **Code, planning, and automation（代码、规划与自动化）** 下，点击 **Codespaces**。
4. 在 **Dotfiles** 部分，勾选 **Automatically install dotfiles（自动安装 dotfiles）**，让每个新建的 Codespace 都会自动应用你的 dotfiles。
5. 点击 **Select repository（选择仓库）**，然后选择当前的课程仓库作为安装 dotfiles 的来源。

### :keyboard: 实操环节: 向仓库添加一个 `dotfile` 并运行 Codespace

1. 进入仓库主页。
2. 点击页面中间的 **Code** 按钮。
3. 在弹出的窗口中选择 **Codespaces** tab。
4. 点击 **Create codespace on main（在 main 分支上创建 Codespace）**。
   > 需要等待大约 **2 分钟**，环境会自动启动。
5. 确认你的 Codespace 已经运行。此时浏览器应打开一个基于 VS Code 的在线编辑器，并带有终端窗口，例如下图所示：

   ![codespace1](https://user-images.githubusercontent.com/26442605/207355196-71aab43f-35a9-495b-bcfe-bf3773c2f1b3.png)

6. 在 VS Code 的文件管理器中创建一个新文件：`setup.sh`。
7. 在文件中输入以下内容：
   ```bash
   #!/bin/bash

   sudo apt-get update
   sudo apt-get install sl
   echo "export PATH=\$PATH:/usr/games" >> ~/.bashrc
   ```
8. 保存文件。
   > **提示**：VS Code 会自动保存。
9. 在终端中执行以下命令提交文件：
   ```shell
   git add setup.sh --chmod=+x
   git commit -m "Adding setup.sh from the codespace!"
   ```
10. 将更改推送到远程仓库：
    ```shell
    git push
    ```
11. 返回仓库主页，确认 `setup.sh` 文件已成功上传。
12. 关闭当前的 Codespace 页面。
13. 再次点击 **Create codespace on main** 按钮创建新环境。
    > 等待约 **2 分钟**，环境将再次自动启动。
14. 确认 Codespace 已运行，并且 `setup.sh` 文件已出现在编辑器中。
15. 在终端中输入以下命令：
    ```shell
    sl
    ```
16. 你的终端上会出现一个 “跑火车” 的动画。
17. 等待约 20 秒后刷新此页面（即你当前查看的教程页面）。[GitHub Actions](https://docs.github.com/en/actions) 会自动检测进度并跳转到下一步。

<footer>

<!--
  <<< Author notes: Footer >>>
  Add a link to get support, GitHub status page, code of conduct, license link.
-->

---

Get help: [Post in our discussion board](https://github.com/orgs/skills/discussions/categories/code-with-codespaces) &bull; [Review the GitHub status page](https://www.githubstatus.com/)

&copy; 2023 GitHub &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)

</footer>
