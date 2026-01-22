# QuickSave 外部资源清单

## 一、阿里云服务（必须）

### 1.1 需要开通的服务

| 服务 | 用途 | 计费方式 | 预估月费用 |
|------|------|----------|------------|
| **函数计算 FC** | 后端 API 服务 | 按调用量 | 免费额度内 |
| **表格存储 Tablestore** | 主数据库 + 搜索 | 按存储和读写 | ~¥10-50 |
| **对象存储 OSS** | 图片/文件存储 | 按存储和流量 | ~¥10-30 |
| **短信服务** | 手机号验证码登录 | 按条数 ¥0.045/条 | ~¥20-100 |
| **API 网关**（可选） | 统一 API 入口 | 按调用量 | 免费额度内 |

### 1.2 开通步骤

```bash
# 1. 登录阿里云控制台
https://www.aliyun.com/

# 2. 开通服务（按顺序）
- 函数计算 FC：https://fc.console.aliyun.com/
- 表格存储：https://otsnext.console.aliyun.com/
- 对象存储 OSS：https://oss.console.aliyun.com/
- 短信服务：https://dysms.console.aliyun.com/

# 3. 创建 AccessKey
https://ram.console.aliyun.com/manage/ak
```

### 1.3 需要配置的资源

| 资源 | 配置项 | 说明 |
|------|--------|------|
| FC | 服务名、函数名 | quicksave-api |
| Tablestore | 实例名、表名 | quicksave-db |
| OSS | Bucket 名称 | quicksave-files |
| 短信 | 签名、模板 | 需要审核 |

### 1.4 需要获取的凭证

- [ ] AccessKey ID
- [ ] AccessKey Secret
- [ ] Tablestore 实例访问地址
- [ ] OSS Bucket 域名
- [ ] 短信签名名称
- [ ] 短信模板 CODE

---

## 二、微信开放平台（必须）

### 2.1 准备工作

| 项目 | 说明 | 状态 |
|------|------|------|
| 企业资质 | 需要企业营业执照 | 待确认 |
| 个人开发者 | 部分功能受限 | 可用 |

### 2.2 需要创建的应用

| 应用类型 | 用途 | 权限 |
|----------|------|------|
| **网站应用** | Web 端微信登录 | 微信登录 |
| **移动应用**（可选） | 未来移动端 | 微信登录 |

### 2.3 开通步骤

```bash
# 1. 注册微信开放平台账号
https://open.weixin.qq.com/

# 2. 创建网站应用
- 填写应用信息
- 设置授权回调域名
- 提交审核

# 3. 获取凭证
- AppID
- AppSecret
```

### 2.4 需要获取的凭证

- [ ] 网站应用 AppID
- [ ] 网站应用 AppSecret
- [ ] 授权回调域名配置

---

## 三、AI 服务（必须）

### 3.1 通义千问（默认）

| 项目 | 说明 |
|------|------|
| 平台 | 阿里云百炼 |
| 模型 | qwen-turbo / qwen-plus |
| 用途 | 标签生成、摘要、分类 |

**开通步骤**：
```bash
# 1. 开通百炼服务
https://bailian.console.aliyun.com/

# 2. 创建 API Key
# 3. 选择模型并获取调用地址
```

**需要获取**：
- [ ] 百炼 API Key
- [ ] 模型 ID（如 qwen-turbo）

### 3.2 备选方案（用户可配置）

| 提供商 | 获取方式 |
|--------|----------|
| OpenAI | https://platform.openai.com/ |
| 本地 Ollama | 用户自行安装 |

---

## 四、域名和证书

### 4.1 需要的域名

| 用途 | 建议域名 | 说明 |
|------|----------|------|
| 官网 | quicksave.app / quicksave.cn | 产品官网 + 下载页 |
| API | api.quicksave.app | 后端接口 |
| Web 管理 | app.quicksave.app | Web 管理面板 |
| 分享页 | s.quicksave.app | 短链分享 |

### 4.2 开通步骤

```bash
# 1. 购买域名
https://wanwang.aliyun.com/

# 2. ICP 备案（国内服务器必须）
https://beian.aliyun.com/

# 3. 申请 SSL 证书（免费）
https://yundun.console.aliyun.com/
```

### 4.3 需要获取的配置

- [ ] 域名
- [ ] ICP 备案号
- [ ] SSL 证书

---

## 五、开发工具和账号

### 5.1 Chrome 开发者账号

| 项目 | 说明 |
|------|------|
| 用途 | 发布 Chrome 扩展 |
| 费用 | 一次性 $5 |
| 地址 | https://chrome.google.com/webstore/devconsole |

### 5.2 Edge 开发者账号

| 项目 | 说明 |
|------|------|
| 用途 | 发布 Edge 扩展 |
| 费用 | 免费 |
| 地址 | https://partner.microsoft.com/dashboard |

### 5.3 代码签名证书（可选）

| 项目 | 说明 |
|------|------|
| 用途 | Windows 安装包签名，避免安全警告 |
| 费用 | ~$200-500/年 |
| 提供商 | DigiCert、Sectigo 等 |

---

## 六、开发前准备清单

### 6.1 必须完成

- [ ] 阿里云账号注册并实名认证
- [ ] 开通 FC 函数计算
- [ ] 开通 Tablestore
- [ ] 开通 OSS
- [ ] 开通短信服务并申请签名/模板
- [ ] 开通通义千问 API
- [ ] 微信开放平台注册
- [ ] 创建网站应用并获取 AppID/Secret
- [ ] 购买域名
- [ ] 完成 ICP 备案（如需要）

### 6.2 开发期间可后补

- [ ] Chrome 开发者账号
- [ ] Edge 开发者账号
- [ ] 代码签名证书
- [ ] SSL 证书配置

---

## 七、费用预估（初期）

| 项目 | 月费用 | 说明 |
|------|--------|------|
| 阿里云 FC | ¥0 | 免费额度内 |
| Tablestore | ¥10-50 | 按实际用量 |
| OSS | ¥10-30 | 按存储量 |
| 短信 | ¥20-100 | 按用户量 |
| AI API | ¥50-200 | 按调用量 |
| 域名 | ¥5-10 | 年付分摊 |
| **合计** | **¥100-400** | 初期用户量少时 |

---

## 八、环境变量清单

开发时需要配置的环境变量：

```env
# 阿里云
ALIYUN_ACCESS_KEY_ID=
ALIYUN_ACCESS_KEY_SECRET=
ALIYUN_REGION=cn-hangzhou

# Tablestore
TABLESTORE_ENDPOINT=
TABLESTORE_INSTANCE=

# OSS
OSS_BUCKET=
OSS_ENDPOINT=

# 短信
SMS_SIGN_NAME=
SMS_TEMPLATE_CODE=

# 微信
WECHAT_APP_ID=
WECHAT_APP_SECRET=

# AI
DASHSCOPE_API_KEY=

# JWT
JWT_SECRET=
JWT_EXPIRE_HOURS=24
```

---

*更新日期: 2026-01-22*
