<!--
  <<< Author notes: Step 2 >>>
  Start this step by acknowledging the previous step.
  Define terms and link to docs.github.com.
-->

## Step 2: 为你的 Codespace 添加自定义镜像!

_干得漂亮! :tada: 你已经成功创建了第一个 Codespace，并通过 VS Code 推送了代码!_

你可以为仓库配置一个**开发容器**，这样无论谁在该仓库中创建 Codespace，都会自动获得一个为项目量身定制的开发环境，其中包含所需的工具和运行时。

**什么是开发容器?** 开发容器（Development containers 或 dev containers） 说白了就是一个 Docker 容器，提供了项目所需的开发环境。
每当你在 Codespace 中工作时，实际上就是在一个虚拟机上的 dev container 中进行开发。

一个 dev container 的配置文件是一个 JSON 文件，它可以让你自定义运行 Codespace 所使用的基础镜像、VS Code 设置、端口转发规则、启动命令等多种参数。

接下来，我们来添加一个 `devcontainer.json` 文件，为 Codespace 指定镜像。

### :keyboard: 实操环节

1. 回到仓库的 **Code** 标签页，点击 **Add file** 下拉按钮，然后选择 `Create new file`。
2. 在文件名输入框中输入以下路径：

   ```
   .devcontainer/devcontainer.json
   ```

3. 在新建的 **.devcontainer/devcontainer.json** 文件中，粘贴以下内容：

   ```jsonc
   {
     // Name this configuration
     "name": "Codespace for Skills!",
     // Use the base codespace image
     "image": "mcr.microsoft.com/vscode/devcontainers/universal:latest",

     "remoteUser": "codespace",
     "overrideCommand": false
   }
   ```
4. 点击 **Commit changes**，并选择 **Commit changes directly to the `main` branch**。
5. 返回仓库的 **Code** 标签页，再次创建一个新的 Codespace。
6. 点击页面中央的绿色 **Code** 按钮。
7. 在弹出的窗口中切换到 **Codespaces** 标签页。
8. 点击 **Create codespace on main** 按钮，或点击标签页上的 `+` 号，为主分支创建一个新的 Codespace。（你会看到之前创建的 Codespace 也列在这里。）
   > 等待大约 **2 分钟**，Codespace 会自动启动。
9. 像之前一样，确认新的 Codespace 是否已成功运行。
   此时使用的镜像是 GitHub Codespaces 提供的默认镜像，其中预装了 Python、Node.js、Docker 等常用运行时和工具。
   完整列表可以查看这里: https://aka.ms/ghcs-default-image 。你可以使用自定义镜像，详细说明见：[配置 codespace 镜像](https://aka.ms/configure-codespace)
10. 等待约 20 秒后刷新当前页面。[GitHub Actions](https://docs.github.com/en/actions) 会自动识别进度并进入下一步。