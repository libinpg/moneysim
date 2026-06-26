# MoneySim · 黑暗金库

> 把记账变成一场可以看见的资产模拟：每一次支出，纸币都会从 3D 金库中飞起、坠入黑暗。

<p align="center">
  <img alt="MoneySim" src="https://img.shields.io/badge/MoneySim-3D%20Money%20Simulator-3ddc84?style=for-the-badge">
  <img alt="Vanilla JS" src="https://img.shields.io/badge/Vanilla-JavaScript-f4b740?style=for-the-badge">
  <img alt="Three.js" src="https://img.shields.io/badge/Three.js-0.160-101114?style=for-the-badge">
  <img alt="Storage" src="https://img.shields.io/badge/Storage-IndexedDB-5ca8ff?style=for-the-badge">
</p>

<p align="center">
  <b>一个无需构建、打开即用的 3D 记账系统。</b><br>
  本地存储、预算追踪、流水管理、图表统计、纸币物理可视化，全都封装在一个 <code>index.html</code> 里。
</p>

---

## 为什么做 MoneySim？

传统记账工具太像表格：输入一笔钱，然后它变成一行冷冰冰的数据。MoneySim 想做一件更直观的事：

**让钱“被看见”。**

当你初始化资产时，金库里会堆满纸币；当你记录支出时，对应金额的纸币会从金库中飞起并消失。它把抽象的消费变成可感知的损失，让预算、余额和消费习惯不再只是数字。

## 核心特性

### 3D 金库可视化

- 基于 Three.js 构建 3D 金库场景
- 按 100、50、20、10、5、1 元面额生成纸币堆
- 支出时触发纸币坠落、粒子消散和音效反馈
- 支持鼠标拖拽旋转视角，查看资产结构

### 完整记账能力

- 支出 / 收入双模式
- 分类、日期、备注管理
- 当前余额、本月收入、本月支出、本月结余统计
- 流水搜索、日期筛选、编辑、删除、撤销
- CSV 导出，便于二次分析

### 预算与分析

- 按分类设置月度预算
- 自动计算预算使用进度
- 本月支出分类分布图
- 日趋势图，帮助发现消费节奏

### 本地优先

- 使用 IndexedDB 持久化保存数据
- 不依赖后端、不上传隐私数据
- 一个 HTML 文件即可运行
- 适合部署到 GitHub Pages、静态托管或本地直接打开

## 快速开始

### 方式一：直接打开

```bash
git clone https://github.com/libinpg/moneysim.git
cd moneysim
open index.html
```

Windows 用户可以直接双击 `index.html`。

### 方式二：本地静态服务

由于页面使用 ES Module 和 CDN import，推荐使用静态服务器获得更稳定的浏览器行为：

```bash
npx serve .
```

或者：

```bash
python -m http.server 5173
```

然后访问浏览器显示的本地地址。

## 使用指南

1. **初始化资产**：首次打开时输入你的真实总资产，MoneySim 会生成对应数量的纸币。
2. **记录支出**：输入金额、分类、日期和备注，点击记录支出，纸币会从金库中消失。
3. **记录收入**：切换到收入模式，收入会让金库重新增长。
4. **查看预算**：在右侧按分类设置预算，观察每月预算消耗情况。
5. **分析流水**：通过图表、搜索和日期筛选复盘消费结构。

## 快捷键

| 快捷键 | 功能 |
| --- | --- |
| `N` | 聚焦记账输入 |
| `S` | 查看统计区域 |
| `C` | 打开分类管理 |
| `Ctrl + Z` | 撤销最新一笔流水 |

## 技术栈

| 模块 | 技术 |
| --- | --- |
| 3D 场景 | Three.js、OrbitControls、InstancedMesh |
| 图标 | Lucide Icons |
| 存储 | IndexedDB |
| 图表 | Canvas 2D |
| 架构 | Vanilla HTML / CSS / JavaScript |
| 部署 | 静态页面 / GitHub Pages |

## 项目结构

```text
moneysim/
├── index.html   # 完整应用：样式、交互、3D 场景、数据存储
└── README.md    # 项目说明文档
```

## 设计亮点

### 1. 用物理隐喻降低理解成本

余额、预算、流水本质上是抽象数据。MoneySim 用“金库”和“纸币消失”的物理隐喻，让用户不需要读复杂报表，也能感受到资产变化。

### 2. 单文件部署

项目不需要构建工具、不需要安装依赖、不需要后端服务。核心逻辑都在 `index.html` 中，降低了学习、修改和部署门槛。

### 3. 隐私友好

所有数据保存在浏览器 IndexedDB 中。除 CDN 加载 Three.js 和 Lucide 外，记账数据不会发送到服务器。

## 适合谁？

- 想养成记账习惯，但讨厌传统表格的人
- 想直观看见消费损失的人
- 想学习 Three.js + 本地存储综合实践的前端开发者
- 想用一个小项目理解“数据可视化如何改变行为”的产品设计者

## Roadmap

- [ ] 支持移动端更细腻的交互布局
- [ ] 增加多账户资产管理
- [ ] 支持月度 / 年度报告导出
- [ ] 增加 PWA 离线安装能力
- [ ] 支持自定义主题和金库皮肤
- [ ] 加入更多消费行为洞察

## 贡献方式

欢迎提交 Issue 或 Pull Request。适合贡献的方向包括：

- UI / UX 优化
- Three.js 性能优化
- 数据导入导出增强
- 图表和统计能力增强
- README、教程、截图和演示文档完善

## 本地开发建议

当前项目是单文件架构，修改门槛很低。建议按下面方式迭代：

```bash
python -m http.server 5173
```

然后在浏览器打开本地地址。修改 `index.html` 后刷新页面即可看到效果。

## License

MIT License

---

<p align="center">
  如果这个项目让你重新感受到了“钱正在流动”，欢迎 Star ⭐ 支持。
</p>
