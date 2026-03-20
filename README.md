# Antom Receive Dev Skill

一个帮助商户完成 Antom 收单机构入驻并创建收款链接的 Claude Code Skill。

## 简介

Antom Receive Dev Skill 可以引导商户完成以下流程：

- 商户注册与授权
- KYB（Know Your Business）认证
- 创建收款链接

当商户想要售卖商品并为其创建收款链接时，该 skill 可以引导用户完成注册、KYB 认证和收款链接创建的全流程。

## 安装

通过 npx 一键安装：

```bash
npx skill add https://github.com/cloudyisland/antom-receive-dev.git
```

安装完成后，Claude Code 会自动识别并加载此 skill。

## 功能特性

| 功能 | 说明 |
|------|------|
| 商户注册 | 引导用户完成 Antom 支付机构商户账户注册 |
| OCR 文档扫描 | 扫描营业执照自动填充 KYB 表单 |
| KYB 认证 | 提交企业信息进行认证审核 |
| 创建收款链接 | 生成可分享的收款 URL |
| 状态监控 | 随时查看账户状态和收款链接统计 |

## 前置要求

首次使用需要安装 CLI 工具：

```bash
npm install -g @zhaoke2021/antom-dashboard-cli
```

## 快速开始

安装 skill 后，只需告诉 Claude 你想要做什么：

```
我想创建一个收款链接
```

或

```
帮我完成 Antom 商户入驻
```

Claude 会自动引导你完成整个流程。

## 工作流程

```
1. 检查状态 → 2. 商户注册 → 3. KYB 认证 → 4. 创建收款链接
```

### 详细步骤

1. **检查状态** - Claude 会首先检查你的当前状态
2. **商户注册** - 如果未注册，引导完成授权
3. **KYB 认证** - 提交企业信息进行审核
4. **创建收款链接** - KYB 通过后创建收款链接

## 项目结构

```
antom-receive-dev/
├── README.md
└── skills/
    └── antom-receive-dev/
        └── SKILL.md          # Skill 定义文件
```

## 支持的币种

- USD（美元）
- EUR（欧元）
- CNY（人民币）
- JPY（日元）
- GBP（英镑）
- AUD（澳元）
- CAD（加元）

## 注意事项

- 本 skill 使用的 `antom-dashboard-cli` 是演示版本
- 所有功能均为 mock 实现，不涉及真实的 Antom 商户门户系统
- 请勿用于生产环境
- KYB 审核在演示版本中会自动通过

## 数据存储

所有数据存储在本地 `~/.antom-cli/` 目录：

```
~/.antom-cli/
├── auth.json           # 授权信息
├── kyb.json            # KYB 认证数据
└── payment-links.json  # 收款链接记录
```

## 开发

如果你想基于此项目开发自己的 skill：

1. Fork 本仓库
2. 修改 `skills/antom-receive-dev/SKILL.md` 文件
3. 发布到你的 GitHub 仓库
4. 使用 `npx skill add <你的仓库地址>` 安装

## 许可证

MIT License

## 相关链接

- [Antom 官网](https://antom.com)
- [Claude Code 文档](https://docs.anthropic.com/claude-code)