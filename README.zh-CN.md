# Android i18n 资源一键批处理工具

<p align="center">
  <strong>零依赖、纯前端本地处理的 Android 国际化资源 (<code>strings.xml</code>) 批处理与安全转义工具。</strong>
</p>

<p align="center">
  <a href="https://rendonglu.github.io/i18n_translate_tool/"><strong>🌐 在线体验 (GitHub Pages)</strong></a>
</p>

<p align="center">
  <a href="README.md">English</a> | 简体中文
</p>

<p align="center">
  <img src="https://img.shields.io/badge/运行环境-Web%20(跨平台)-blue" alt="Platform">
  <img src="https://img.shields.io/badge/安全-100%25%20纯本地计算-brightgreen" alt="Client-Side Only">
  <img src="https://img.shields.io/badge/开源协议-MIT-orange" alt="License">
  <img src="https://img.shields.io/badge/GitHub%20Pages-支持-success" alt="GitHub Pages">
</p>

---

## 🚀 在线体验 (Live Demo)

👉 **[点击直接在浏览器中打开 (GitHub Pages)](https://rendonglu.github.io/i18n_translate_tool/)**

免安装任何依赖，无命令行，无系统授权弹窗，打开即用。

---

## 💡 为什么从终端脚本切换为 Web 工具？

在 Android 多语言开发中，翻译人员或系统导出的 XML 常常包含未转义的单引号 (`'`)、和号 (`&`)，以及历史语言目录映射需求（如 `values-id` &rarr; `values-in`、裁剪不需要的 `values-ur`）。

传统终端脚本（`.sh` / `.command`）存在诸多痛点：
- ❌ **权限拦截与门禁**：macOS Gatekeeper 经常弹出“未知开发者/已损坏”拦截提示，需要手动 `chmod +x`。
- ❌ **系统环境不统一**：强依赖系统的 `perl` 或 `python3` 版本，Windows 同事使用非常麻烦（需配置 WSL 或 Git Bash）。
- ❌ **团队分享门槛高**：每次都要把脚本文件复制到工程或各个同事电脑，排错成本高。

**Web 工具彻底解决以上问题：**
- ✅ **零权限、无拦截**：直接在浏览器沙箱中安全运行，没有任何系统门禁警告。
- ✅ **跨平台一致**：Windows、macOS、Linux 运行结果 100% 一致。
- ✅ **100% 纯本地隐私安全**：所有文件的解压、字符替换、目录结构重组与打包均在**浏览器内存**中完成，**无任何数据上传至服务器**。

---

## ⚡ 核心功能特性

1. **安全字符转义**：
   - `'` &rarr; `\'`（自动幂等：已有斜杠转义的单引号不会重复转义）。
   - `&` &rarr; `&amp;`（严格保护已有实体如 `&amp;`、`&lt;`、`&gt;`、`&quot;`、`&apos;`，不产生 `&amp;amp;`）。
2. **多语言目录改名**：
   - 默认预置 `values-id:values-in`（印尼语目录规范重命名），支持根据项目灵活配置。
3. **语言目录剔除（删除）**：
   - 一键过滤不需要的语言目录（如 `values-ur`）。
4. **三种处理模式**：
   - 📁 **本地目录原地批处理 (推荐)**：基于 Chromium 内核的 *File System Access API* (`showDirectoryPicker`)，直接选择工程 `res` 文件夹，自动在本地备份并原地安全写回。
   - 📦 **通用 ZIP / 文件夹导入导出**：全浏览器通用（Chrome、Safari、Edge、Firefox 均可），拖入文件夹或 ZIP 包，处理完毕后一键下载新 ZIP。
   - ✍️ **单文本即时调试**：随时粘贴单个 `<string>` 片段进行转换校验与结果复制。
5. **实时日志与统计**：详细展示扫描文件数、修改文件数、改名项与跳过项。

---

## 🛠️ 使用方式

### 方式 1：在线直接使用（推荐）
在现代浏览器中直接访问 **[在线体验链接](https://rendonglu.github.io/i18n_translate_tool/)**。

### 方式 2：本地离线使用
1. 克隆或下载本仓库代码。
2. 双击打开 `index.html` 即可离线使用全部功能。

---

## 📦 部署到自己的 GitHub Pages

你可以免费将此项目托管到你自己的 GitHub 账号上：

1. 推送到 GitHub：
   ```bash
   git init
   git add .
   git commit -m "feat: initial commit"
   git branch -M main
   git remote add origin https://github.com/<你的用户名>/<你的仓库名>.git
   git push -u origin main
   ```
2. 进入 GitHub 仓库设置：
   - 点击 **Settings** &rarr; 左侧 **Pages**。
   - 在 **Build and deployment** 下将 **Source** 设为 `Deploy from a branch`。
   - 分支选择 `main`，目录选择 `/ (root)`，点击 **Save**。
3. 部署完成后，即可在 `https://<你的用户名>.github.io/<你的仓库名>/` 访问。

---

## 📄 开源协议

[MIT License](LICENSE) © 2026 rendonglu
