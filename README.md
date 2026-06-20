# 智链简历 (SmartChain Resume)

<div align="center">

**AI 驱动的智能简历系统与云端招聘解决方案**

**AI-Powered Smart Resume System & Cloud Recruitment Solution**

[在线演示 / Live Demo](https://Ablu6669.github.io/zzh_resume-system) · [问题反馈 / Issues](https://github.com/Ablu6669/zzh_resume-system/issues)

</div>

---

## 📖 项目简介 / About

**智链简历**是一款面向线下招聘会场景的智能简历系统，致力于解决招聘会现场简历格式混乱、数据难以结构化的痛点。

求职者通过标准化模板填写简历并生成唯一识别码；企业端扫码或输入识别码即可快速查询、预览、导出简历，实现招聘数据的高效流转。

**SmartChain Resume** is an intelligent resume system designed for offline job fairs. It tackles the pain points of inconsistent resume formats and unstructured data at recruitment events.

Job seekers fill in their resumes via a standardized template and receive a unique ID code. Recruiters can scan or enter the code to instantly retrieve, preview, and export resumes — enabling efficient data flow throughout the hiring process.

> 💡 本项目为 **腾讯学堂 AI-HR 线上实战营** 自定义赛道作业 Demo。
>
> 💡 This project is a Demo for the **Tencent Academy AI-HR Online Bootcamp** open-track assignment.

---

## ✨ 功能特性 / Features

### 👤 求职者端 / Job Seeker

| 功能 / Feature | 说明 / Description |
|---|---|
| 📝 标准化简历编辑 / Structured Resume Editor | 多步骤表单，结构化管理个人信息、教育、工作、项目、技能 / Multi-step form for personal info, education, work, projects & skills |
| 🎨 实时预览 / Live Preview | 编辑同时实时渲染，所见即所得 / WYSIWYG rendering as you type |
| 📄 PDF 导出 / PDF Export | 一键生成高质量 PDF / One-click high-quality PDF generation |
| ☁️ 云端保存 / Cloud Save | 数据加密存储至 GitHub Gist，生成唯一识别码 / Encrypted storage to GitHub Gist with unique share code |

### 🏢 企业端 / Recruiter

| 功能 / Feature | 说明 / Description |
|---|---|
| 🔍 识别码查询 / Code Lookup | 输入识别码秒级调出简历 / Instant resume retrieval by code |
| 👁️ 在线预览 / Online Preview | 浏览器内查看完整简历 / View full resume in browser |
| 📊 Excel 批量导出 / Excel Export | 导出为 Excel 便于 HR 统一管理 / Export to Excel for centralized HR management |
| 📱 移动端适配 / Mobile Responsive | 手机 / 平板 / 电脑多端访问 / Supports mobile, tablet & desktop |

---

## 🏗️ 系统架构 / Architecture

```
┌─────────────────┐     HTTPS      ┌──────────────────────┐     GitHub API     ┌─────────────────┐
│   Browser SPA   │ ────────────>  │  Tencent Cloud SCF   │ ────────────>      │  GitHub Gist    │
│  (Single File)  │ <────────────  │  (Server-side Proxy) │ <────────────      │  (Cloud Storage)│
└─────────────────┘     JSON       └──────────────────────┘     JSON           └─────────────────┘
        │                                                                │
        v                                                                v
┌─────────────────┐                                           ┌─────────────────┐
│  localStorage   │                                           │  GitHub Token   │
│  (Local Cache)  │                                           │  (Server-only)  │
└─────────────────┘                                           └─────────────────┘
```

### 架构亮点 / Architecture Highlights

| 设计点 / Design | 说明 / Description |
|---|---|
| **Token 安全 / Token Security** | GitHub Token 仅存在于 SCF 服务端，前端代码零敏感信息 / Token stays server-side only; zero sensitive data in frontend code |
| **国内访问 / China Accessibility** | 腾讯云 SCF 国内节点，避免境外服务访问限制 / Tencent Cloud SCF domestic nodes avoid overseas access restrictions |
| **零成本运行 / Zero Cost** | SCF 按调用计费 + GitHub Gist 免费存储，个人使用近乎免费 / SCF pay-per-call + free Gist storage = near-zero cost |
| **单文件部署 / Single File Deploy** | Vite 打包为单个 HTML 文件，通过 GitHub Pages 免费托管 / Bundled into a single HTML file, hosted free on GitHub Pages |

---

## 🛠️ 技术栈 / Tech Stack

### 前端 / Frontend
- **框架 / Framework**：React 19 + TypeScript
- **构建工具 / Build Tool**：Vite 8 + vite-plugin-singlefile
- **样式 / Styling**：Tailwind CSS 3 + Lucide React
- **路由 / Router**：React Router DOM 7
- **导出 / Export**：jsPDF (PDF) + SheetJS xlsx (Excel)
- **二维码 / QR Code**：qrcode.react

### 后端 / Backend
- **云服务 / Cloud**：腾讯云 SCF (Serverless Cloud Function)
- **存储 / Storage**：GitHub Gist API
- **安全代理 / Proxy**：SCF acts as a proxy between frontend and GitHub API; Token is server-side only

### 部署 / Deployment
- **静态托管 / Static Hosting**：GitHub Pages
- **构建产物 / Build Output**：`dist-single/index.html`

---

## 📌 改进方向 / Roadmap

- [ ] 增加用户账号体系，支持多份简历管理 / User account system with multi-resume management
- [ ] 企业端支持批量导入识别码、批量导出 PDF / Batch code import & PDF export for recruiters
- [ ] 简历模板多样化，支持更多排版风格 / More resume templates and layout styles
- [ ] 接入 AI 能力，实现简历内容智能优化建议 / AI-powered resume content suggestions

---

## 📄 License

本项目采用 [Apache License 2.0](./LICENSE) 开源。允许商用、修改和分发，但须保留原作者版权声明。

This project is licensed under the [Apache License 2.0](./LICENSE). Commercial use, modification, and distribution are permitted with proper attribution.

---

## 🙏 致谢 / Acknowledgements

- 腾讯学堂 AI-HR 线上实战营 / Tencent Academy AI-HR Online Bootcamp
- [React](https://react.dev/)、[Vite](https://vitejs.dev/)、[Tailwind CSS](https://tailwindcss.com/) 等开源项目 / and other open-source projects
- [GitHub Gist](https://gist.github.com/) 免费存储 / free storage
- [腾讯云 SCF](https://cloud.tencent.com/product/scf) Serverless 计算能力 / serverless computing

---

<div align="center">

**⭐ 如果这个项目对你有帮助，欢迎 Star！/ If this project helps you, please give it a Star!**

</div>
