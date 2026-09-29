# 柠檬云全场景开票

本公开源码包只包含 `invoice-issue` 业务 Skill。公共的 Go 实现、Node.js 打包脚本和依赖代码保留在 `go-script/` 中，便于查看、构建和维护。

## 描述

**名字：** 发票开具（免费1万张/每月）_批量开票_文字/语音开票_批量开发票_文字/语音开发票_财务会计全场景开票_柠檬云发票

**描述：**

柠檬云AI财税开放平台：发票开具SKill（每月免费享10000张开票额度），专为财务、会计、财税从业者打造的全场景发票开具与管理工具，覆盖文字 / 语音单张开票、ERP 订单批量开票、非结构化资料开票三大核心场景，提供开票全流程标准化服务，一站式解决人工逐票核对效率低、重复报销管控难、开票信息易出错等财税工作痛点。
✅多源开票资料智能解析：支持文字录入、ERP / 电商订单 Excel、合同等多格式开票资料解析，自动提取发票抬头、税号、金额等核心关键字段，智能自动赋码，告别会计人工逐条录入的繁琐。
✅信息校验与风控查重：自动核对票面全量数据，生成开票预览，需人工确认后才执行开票操作；内置发票真伪核验、重复开票查重能力，从源头规避信息差错与重复报销风险，保障财税合规。
✅发票开具与一站式交付：一键完成发票开具，同步获取税局官方发票 PDF 原件；支持一键交付收票方，自动生成标准化发票台账，满足财务对账、报销管理、核算归档等多场景需求。
适配企业财务核算、代理记账、电商开票等各类财税工作场景，轻量化部署开箱即用，以数字化能力替代人工重复操作，助力企业提升发票处理效率，管控财税风险。

详细的 Skill 规则、使用前准备和安装更新流程见 [`invoice-issue/README.md`](./invoice-issue/README.md)、[`invoice-issue/SKILL.md`](./invoice-issue/SKILL.md) 和 [`invoice-issue/invoice-issue-install.md`](./invoice-issue/invoice-issue-install.md)。

## 目录结构

- `invoice-issue/`：当前 Skill 的说明、安装文档、引用资料和资源。
- `go-script/`：Go 命令行实现、公共库和生产打包脚本。

## 生产构建

构建要求 Node.js 20+ 和 Go 1.24+。请在仓库根目录执行：

```powershell
npm ci
node go-script/build.js --env prod invoice-issue
```

生产发布物生成在 `dist/Skills/invoice-issue/`。运行时 ZIP 包不包含 `bin/**` 二进制文件，安装时按安装文档下载当前平台对应的二进制。

## 配置与数据安全

- API 凭据由使用者在本地工作区配置，不应写入源码、文档或日志。
- 生产接口通过 `go-script/config/prod.json` 注入发布包。
- 安全问题请按照 [SECURITY.md](SECURITY.md) 私下报告。

## 许可证

本项目自有代码、文档和资源文件采用 [MIT License](LICENSE)；第三方组件与字体许可见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。
