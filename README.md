# VOLT // 无畏经理人

> 一个无需后端、打开即玩的 VALORANT 风格电竞战队经营游戏。
>
> 玩家将从一间租来的训练室和一支年轻阵容开始，完成招募、训练、战术准备、赛事经营、赞助签约与任务挑战，最终从次级联赛一路冲击 VCT CN。

![Version](https://img.shields.io/badge/version-1.0.0-e85b68)
![Platform](https://img.shields.io/badge/platform-Web%20%2F%20GitHub%20Pages-67e3ee)
![Dependencies](https://img.shields.io/badge/dependencies-none-8bd450)

## 在线体验

如果项目已经部署到 GitHub Pages，可以访问：

```text
https://laogaofirefly.github.io/Valorant-manager-v2/
```

实际地址以仓库 Pages 设置为准。

## 项目简介

VOLT Manager 是一个纯前端的电竞经理模拟游戏原型，采用原生 HTML、CSS 和 JavaScript 编写，不依赖后端服务，也不需要构建工具。

游戏核心目标：

```text
创建经理 → 组建阵容 → 训练与备战 → 参加次级联赛
→ 积累资金、声望与粉丝 → 晋级挑战者联赛 → 冲击 VCT CN
```

当前版本为 `v1.0.2`，重点完成了首次剧情、基础经营循环、任务系统、沉浸式剧情界面和本地存档。

## 核心特色

- 首次打开自动进入开场剧情
- 沉浸式赛博风格剧情创建界面
- 资金、工资、房租和赞助收入管理
- 初始五人阵容与选手市场
- 训练、准备度、士气和团队化学反应
- 次级联赛、挑战者联赛和 VCT CN 成长路线
- 每周任务、进度追踪和奖励领取
- 赛程与赛事页面
- 战术实验室、俱乐部、青训和财务模块
- 响应式布局，支持手机和桌面浏览器
- 浏览器本地存档、自动备份和快捷保存

## 游戏流程

### 1. 首次启动

首次打开且浏览器中没有存档时，游戏会直接进入开场剧情：

> 每一支强队，都曾从黑暗中开始。

输入经理代号后，点击“进入故事”，也可以在输入框中按 `Enter` 开始生涯。

系统会自动创建：

- 经理姓名
- 战队名称：`姓名 + 电竞`
- 初始预算：`¥1,000,000`
- 初始战队：5 名 VOLT Academy 选手
- 初始赛事级别：次级联赛
- 初始声望：300
- 初始团队化学反应：55

### 2. 管理中心

管理中心可以查看当前月份、赛事级别、运营资金、月度支出、赞助收入、赛季战绩、赛事信息、赞助合同、本周任务以及版本信息。

点击“推进一周”可以推进经营时间。每周会刷新行动点、降低部分士气，并在满足条件时进入下个月。

### 3. 选手市场

选手市场用于查看和签约选手。签约时会检查赛事级别、选手签约状态、阵容人数和签约保证金。

阵容最多保留 5 名首发和 2 名替补。不同赛事级别会限制可直接签约的选手强度，声望提升后可以接触更高水平的选手。

### 4. 训练与战术

训练和战术操作会影响选手能力、比赛准备度、地图胜率、团队化学反应、士气和比赛胜率。训练会消耗行动资源，需要在训练、准备和比赛之间进行平衡。

### 5. 赛事与比赛

| 阶段 | 赛事 | 主要特点 |
| --- | --- | --- |
| 1 | 次级公开赛 | BO1 小组赛，前四进入 BO3 淘汰赛 |
| 2 | Challengers CN | BO3 常规赛，积分制，前四进入季后赛 |
| 3 | VCT CN | 官方赛区风格的 BO3 高级赛事 |

比赛结果会影响胜负记录、声望、资金、晋级进度和任务进度。

### 6. 赞助与财务

赞助合同提供每月收入和粉丝增长，但不同合同有不同解锁条件。

| 赞助商 | 月收入 | 粉丝 | 解锁条件 |
| --- | ---: | ---: | --- |
| 社区电竞馆 | ¥30,000 | +100 | 默认开放 |
| 硬件品牌 | ¥70,000 | +250 | 声望达到 700 |
| 全国饮料品牌 | ¥140,000 | +500 | 挑战者联赛及声望达到 1400 |

每月净变化计算方式：

```text
净变化 = 赞助收入 - 选手工资 - 训练室房租
```

## 任务系统

管理中心包含“本周任务”面板。任务会追踪实际行为，并提供额外资金与声望奖励。

| 任务 | 目标 | 资金奖励 | 声望奖励 |
| --- | --- | ---: | ---: |
| 训练计划 | 完成 2 次训练或专项培养 | ¥12,000 | +8 |
| 赛前准备 | 准备度达到 60 | ¥18,000 | +10 |
| 磨合阵容 | 化学反应达到 65 | ¥15,000 | +9 |
| 拿下一胜 | 赢得 1 场正式比赛 | ¥30,000 | +18 |
| 建立名声 | 累计获得 50 点声望 | ¥22,000 | +12 |

任务状态包括进行中、已完成等待领取、已领取。领取后会立即加入资金和声望，并写入最近完成记录。

## 存档机制

游戏使用浏览器 `localStorage` 保存数据：

```text
volt-save
```

每次保存时还会生成备份：

```text
volt-save-backup
```

保存内容包括经理信息、资金、财务、赛事级别、选手合同、赞助、声望、士气、化学反应、比赛历史、任务状态和剧情状态。

### 保存方式

关键操作会自动保存，也可以使用：

```text
Ctrl + S
```

macOS 使用 `Command + S`。

### 清除存档

在浏览器开发者工具 Console 中执行：

```js
localStorage.removeItem('volt-save');
localStorage.removeItem('volt-save-backup');
location.reload();
```

### 恢复备份

如果页面脚本正常加载，可以执行：

```js
restoreV10Backup();
```

该操作会恢复 `volt-save-backup` 并刷新页面。

## 快捷键

| 快捷键 | 功能 |
| --- | --- |
| `Ctrl / Command + S` | 保存当前进度 |
| `Enter` | 在剧情姓名输入框中开始生涯 |
| `Esc` | 关闭主菜单 |

## 本地运行

直接双击 `index.html` 即可运行基础版本。更推荐使用静态服务器：

```bash
cd /path/to/Valorant-manager-v2
python3 -m http.server 8080
```

然后访问 `http://localhost:8080`。

也可以使用：

```bash
npx serve .
```

## 部署到 GitHub Pages

1. 将项目推送到 GitHub 仓库。
2. 打开仓库 `Settings` → `Pages`。
3. 选择 `Deploy from a branch`。
4. 分支选择 `main`，目录选择 `/ (root)`。
5. 保存并等待部署完成。

项目不需要构建命令，也不需要安装 Node.js 依赖。

命令行示例：

```bash
git clone https://github.com/laogaofirefly/Valorant-manager-v2.git
cd Valorant-manager-v2
git add .
git commit -m "deploy VOLT Manager"
git push origin main
```

## 项目结构

```text
Valorant-manager-v2/
├── index.html       # 页面入口、基础布局和资源引用
├── app.js           # 游戏状态、页面渲染、经营逻辑和交互
├── style.css        # 视觉样式、动画和响应式规则
├── dashboard/       # 管理中心模块
├── roster/          # 选手市场模块
├── schedule/        # 赛事与赛程模块
├── tactics/         # 战术实验室模块
├── club/            # 俱乐部模块
├── academy/         # 青训模块
├── finance/         # 财务与赞助模块
├── 404.html         # GitHub Pages 404 页面
└── README.md        # 项目说明文档
```

## 技术说明

- HTML5
- CSS3
- 原生 JavaScript
- Browser LocalStorage
- GitHub Pages
- Google Fonts：Barlow Condensed、Noto Sans SC

项目无后端、无数据库、无构建流程、无第三方运行时依赖。游戏数据只保存在玩家自己的浏览器中。

主要状态对象：

```js
state.money           // 当前资金
state.playerName      // 经理姓名
state.clubName        // 战队名称
state.division        // 当前赛事级别
state.month           // 当前月份
state.signed          // 已签约选手 ID
state.contracts       // 选手合同
state.sponsors        // 已签约赞助商
state.reputation      // 战队声望
state.chemistry       // 团队化学反应
state.prep            // 比赛准备度
state.storyFlags      // 剧情状态
state.missions        // 任务状态
state.taskStats       // 任务统计
```

## 开发与修改

### 添加任务

在任务系统 `TASK_POOL` 中添加任务对象：

```js
{
  id: 'fans',
  title: '扩大影响力',
  desc: '累计获得 500 名粉丝',
  target: 500,
  reward: 25000,
  rep: 15,
  icon: '✦',
  get: state => Number(state.sponsorFans || 0)
}
```

### 修改主题色

`style.css` 顶部的 CSS 变量控制主要颜色：

```css
:root {
  --red: #ff5868;
  --cyan: #67e3ee;
  --yellow: #f0c674;
}
```

### 修改版本信息

版本信息位于 `app.js` 的 1.0 发布扩展中：

```js
const VERSION = '1.0.0';
```

修改版本时建议同步更新 README、Git commit、Git tag 和 `index.html` 的资源版本参数。

## 质量检查

提交前建议执行：

```bash
node --check app.js
git status
git diff --check
```

浏览器测试重点：

- 首次启动是否自动进入剧情
- 输入姓名后能否创建生涯
- 刷新后存档是否存在
- 任务完成后能否领取奖励
- 推进一周后时间和财务是否正确
- 手机宽度下是否横向溢出
- 主菜单、新建生涯和已有存档流程是否正常

## 版本记录

### v1.0.2

首个稳定版本，包含：

- 首次启动自动进入剧情
- 沉浸式剧情创建界面
- 战队经营基础循环
- 选手市场与签约
- 训练、战术和赛事系统
- 资金、工资、房租和赞助系统
- 每周任务与奖励
- 本地存档和自动备份
- Ctrl / Command + S 快捷保存
- 移动端响应式界面
- VOLT Manager 1.0 发布信息

## 已知限制

- 当前为纯本地单机版本，没有账号系统和云存档。
- 清除浏览器站点数据会删除本地生涯。
- 不同浏览器、设备之间不会自动同步存档。
- 部分赛事、选手和规则为游戏化设定，并非官方实时数据。
- 当前没有多人联机、在线排行榜或服务端校验。
- 视觉素材主要由 CSS 和文本构成，没有使用官方游戏素材文件。

## 商标与内容声明

本项目是独立的非官方游戏原型/练习项目，与 Riot Games、VALORANT、VCT 或任何相关战队、选手及赛事官方不存在隶属、授权或合作关系。

项目中使用的 VALORANT、VCT 等名称仅用于说明游戏风格和赛事生态。正式商业发布、公开分发官方素材或进行品牌化运营前，请自行确认 Riot Games 及其他相关权利人的商标、版权和内容使用许可。

## 贡献建议

欢迎通过 Issue 或 Pull Request 提交 Bug 反馈、UI 改进、平衡性建议、新任务、新赛事、经营事件、移动端问题和文档修正。

提交问题时建议附上：

1. 使用的浏览器和设备。
2. 复现步骤。
3. 是否已有本地存档。
4. 控制台错误信息。
5. 相关截图或录屏。

## 致谢

感谢所有参与测试、提供玩法建议并帮助完善 VOLT Manager 1.0 的玩家。

---

**VOLT Manager 1.0**
从次级赛场开始，向 VCT CN 进发。

### v1.0.2
- 重构启动页为唯一权威入口，避免多个主界面叠加。
- 修复主界面与游戏管理壳同时显示的问题。
- 修复初始化异常导致赛程与赛事页面无法打开的问题。
- 更新静态资源版本号，避免 GitHub Pages 缓存旧脚本。
