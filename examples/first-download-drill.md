# 第一次用 MDM 演练 | First MDM drill: right file, safe install, first downloads

把「下对文件、安全装上、完成第一次下载」完整走一遍：

1. **只从官方页下**：打开原仓 GitHub Releases 页，选 `...-setup.exe`（不确定就选它）。不要从任何第三方下载站拿包。
2. **过 SmartScreen**：第一次运行时若弹出 "Windows protected your PC"，点 More info → Run anyway。这是它未做代码签名的固定提示；若你下的包不是来自 Releases 官方页，这一步立刻停下。
3. **选语言**：安装时选你的语言（西班牙语、葡萄牙语都在 86 种里），之后可在 View → Language 里改。
4. **装扩展**：Firefox 从附加组件站装、Chrome 从网上应用店装。心里记住差异：YouTube 上的下载按钮在 Firefox 版有、Chrome 商店版被商店政策禁了。
5. **下第一个文件**：在浏览器里点一个大文件下载，确认它被 MDM 接住、断点续传可用（中途暂停再恢复一次）。
6. **排一晚夜间队列**：建一个队列，塞两个大文件，设夜间开始、完成后关机——这是它替 IDM 最实在的一件日常事，亲手跑通一次。
