<!--
  <<< Author notes: Step 3 >>>
  Start this step by acknowledging the previous step.
  Define terms and link to docs.github.com.
-->

## Step 3: 自定义你的codespace!

_:tada: 你成功创建了一个使用自定义镜像的 Codespace!_

你还可以进一步定制你的 Codespace，例如安装 VS Code 插件、添加功能、设置host等，让开发环境完全符合你的工作习惯。

接下来，我们将修改 `devcontainer.json` 文件，为 Codespace 添加一些自定义配置。

### :keyboard: 实操环节：在 `devcontainer.json` 文件中添加自定义设置

1. 打开仓库中的 `.devcontainer/devcontainer.json` 文件。
2. 在文件最后一个 `}` 之前，加入以下内容：

   ```jsonc
    ,
    // 当容器创建时自动安装的 VS Code 插件
    "customizations": {
        "vscode": {
            "extensions": [
                "GitHub.copilot"
            ]
        },
        "codespaces": {
            "openFiles": [
                "codespace.md"
            ]
        }
    }
   ```
3. 点击 **Commit changes**，并选择 **Commit changes directly to the `main` branch**。
4. 回到仓库首页，再次创建一个新的 Codespace。
5. 点击页面中央的绿色 **Code** 按钮。
6. 在弹出的窗口中切换到 **Codespaces** 标签页。
7. 确认当前活跃的 Codespace 数量未达到上限（通常最多允许 2 个）。详情可参考 [了解 Codespace 生命周期](https://docs.github.com/en/codespaces/getting-started/understanding-the-codespace-lifecycle)。
   > **提示**：若想停止正在运行的 Codespace，可点击 **•••** 按钮（位于 **●Active** 旁边），然后选择 **Stop codespace**。
8. 点击 **Create codespace on main** 按钮创建新的 Codespace。
   > 等待约 **2 分钟**，Codespace 将自动启动。
9. 和之前一样，确认你的 Codespace 已成功运行。
10. 启动后，`codespace.md` 文件会自动在 VS Code 编辑器中打开。
11. `GitHub Copilot` 插件也会出现在 VS Code 的扩展列表中。

通过这一配置，我们让 Codespace 在启动时自动安装插件，并在启动后自动打开指定文件。

接下来，我们再让 Codespace 在创建时自动执行一段代码！

### :keyboard: 实操环节：让 Codespace 创建后自动执行代码

1. 编辑 `.devcontainer/devcontainer.json` 文件。
2. 在最后一个 `}` 之前加入以下内容：
   ```jsonc
    ,
    "postCreateCommand": "echo '# Writing code upon codespace creation!'  >> codespace.md"
   ```
3. 点击 **Commit changes**，并选择 **Commit changes directly to the `main` branch**。
4. 回到仓库首页，创建一个新的 Codespace。
5. 点击页面中央的绿色 **Code** 按钮。
6. 在弹出的窗口中切换到 **Codespaces** 标签页。
7. 点击 **Create codespace on main** 按钮。
   > 等待大约 **2 分钟**，Codespace 会自动启动。
8. 和之前一样，确认 Codespace 已成功运行。
9. 打开 `codespace.md` 文件，确认其中新增了以下内容：
   ```
   Writing code upon codespace creation!
   ```
10. 等待约 20 秒后刷新当前页面，[GitHub Actions](https://docs.github.com/en/actions) 会自动识别并进入下一步。