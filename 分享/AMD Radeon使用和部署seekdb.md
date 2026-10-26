# AMD Radeon 使用和部署 seekdb

本文按“兑换算力 → 启动 seekdb → 保存部署信息 → 课程与考券”的顺序操作。

## 一、注册并兑换算力
### 1. 注册 AMD 开发者账号
打开 [AMD 开发者平台](https://developer.amd.com.cn/login?source=0u9Eqno7R)，首次使用先注册，再登录。验证码有效时间较短，建议先填好其他信息，再发送验证码；密码按页面要求设置。

<img src="https://cdn.nlark.com/yuque/0/2026/png/28749819/1792983212063-582107f7-c310-43a6-9785-35a2259f722c.png" width="3024" title="AMD 开发者平台注册与登录入口" crop="0,0,1,1" id="OKYpR" class="ne-image">

### 2. 兑换算力券
登录后，在首页点击“积分免费兑换”，进入权益页面领取算力额度。

<img src="https://cdn.nlark.com/yuque/0/2026/png/28749819/1792983211850-6a5e57eb-c9dc-4014-88d0-13a51b0dd01b.png" width="3352" title="首页的积分免费兑换入口" crop="0,0,1,1" id="OdrhT" class="ne-image">

选择兑换小时数，点击“立即兑换”。原手册说明每账号每日最多兑换 20 小时，具体可兑换额度以页面显示为准。

<img src="https://cdn.nlark.com/yuque/0/2026/png/28749819/1792983211433-771a635f-39e0-4853-9491-48531751fab8.png" width="3354" title="选择算力券兑换小时数" crop="0,0,1,1" id="dM5bB" class="ne-image">

兑换完成后，在兑换记录中点击“查看云算力券”，再点击“复制链接”，供下一步兑换使用。

<img src="https://cdn.nlark.com/yuque/0/2026/png/28749819/1792983211543-607f5252-bb0f-43fa-917c-c57b87d93525.png" width="3350" title="兑换记录中的查看云算力券入口" crop="0,0,1,1" id="OXYy7" class="ne-image">

### 3. 将算力券兑换到 Radeon Cloud
返回首页，点击“AMD 开发者云”，按提示使用 GitHub 或魔搭账号登录。

<img src="https://cdn.nlark.com/yuque/0/2026/png/28749819/1792983211820-33d69ce9-4ad3-4367-b487-e1dff8988b77.png" width="3342" title="进入 AMD 开发者云" crop="0,0,1,1" id="gUu72" class="ne-image">

打开右上角用户名下的 **Profile**，点击 **Redeem Credits**；在弹出的 **Coupon Code** 输入框中粘贴刚复制的内容，再点击 **Redeem**。看到兑换成功提示后，确认可用额度已增加。

<img src="https://cdn.nlark.com/yuque/0/2026/png/28749819/1792983213348-42a61c5e-c876-4ed0-b02d-6bdfd69e4b1d.png" width="3354" title="Profile 页面中的 Redeem Credits 入口" crop="0,0,1,1" id="NqJ9G" class="ne-image">

## 二、启动 seekdb 并完成实验
### 1. 创建实验环境
进入 **Gallery**，搜索 `seekdb`，找到 **seekdb-hipvs**，点击 **Launch**。该模板包含 seekdb、hipVS 预编译库和测试样例。

<img src="https://cdn.nlark.com/yuque/0/2026/png/28749819/1792983213513-eb718ddd-79c2-44a8-a52a-6a550589ce41.png" width="2992" title="搜索 seekdb 并启动 seekdb-hipvs 模板" crop="0,0,1,1" id="GxFA5" class="ne-image">

等待工作空间初始化。显示 **Your workspace is ready** 后，点击 **Open Notebook** 进入实验。

<img src="https://cdn.nlark.com/yuque/0/2026/png/28749819/1792983213888-aa4b10aa-b7f7-40d0-af53-6693349fd74b.png" width="3322" title="工作空间准备完成后打开 Notebook" crop="0,0,1,1" id="o8Nma" class="ne-image">

### 2. 按顺序执行 Notebook
阅读每段说明，依次选中代码单元并点击执行按钮，在单元下方查看结果。按 Notebook 顺序完成环境检查、启动数据库和后续数据实验。

<img src="https://cdn.nlark.com/yuque/0/2026/png/28749819/1792983213825-e5f794c7-d13d-4bf9-b26b-604f42266845.png" width="1853" title="依次选择并执行 Notebook 代码单元" crop="0,0,1,1" id="kVRXK" class="ne-image">

先运行环境与硬件自检，检查 AMD GPU、ROCm、seekdb 二进制及相关库是否正常。

<img src="https://cdn.nlark.com/yuque/0/2026/png/28749819/1792983214212-1d9825d7-5def-4e02-bb74-5e61585190bd.png" width="1823" title="环境与硬件自检结果" crop="0,0,1,1" id="a3hof" class="ne-image">

继续执行启动 seekdb 的单元，确认输出 `observer ready` 和 seekdb 版本信息。**保存部署成功的结果截图**，后续登记会用到。

<img src="https://cdn.nlark.com/yuque/0/2026/png/28749819/1792983215142-18ea319b-69f3-49a2-b878-af26669cc27a.png" width="2732" title="seekdb 启动成功与版本信息" crop="0,0,1,1" id="t5UVe" class="ne-image">

## 三、保存部署 UUID 并释放实例
### 1. 保存部署信息
在 **seekdb 运行目录**下找到 `run/telemetry.json`，打开文件，复制 `content.id` 的值，即本次部署的 UUID，同时保存截图。

例如，文件中出现 `"content": {"id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx", ...}`，应登记 `id` 对应的完整字符串。请填写自己实例的值。

领取考券前，准备好：

+ seekdb 部署成功截图。
+ 部署 UUID 及对应截图。
+ OBCA 课程学习完成截图。

### 2. 释放实验环境
**先保存好截图和 UUID，再到 Profile 的 Active Instance 中点击 Destroy，释放实例，避免持续消耗算力额度。**

下图是释放完成后的状态，显示 **No Active Instance**。

<img src="https://cdn.nlark.com/yuque/0/2026/png/28749819/1792983215205-570efa6c-9e56-44db-b54f-069def35a893.png" width="2972" title="释放实例后的 No Active Instance 状态" crop="0,0,1,1" id="dE9id" class="ne-image">
