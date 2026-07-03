# Chicago-Crime-Sim

Chicago-Crime-Sim 是一款专为居民、游客以及城市规划师设计的社区尺度空间安全监测与交互式模拟移动应用。项目打破了传统静态地图的限制，将复杂的城市大数据与机器学习模型（AI Modeling）转化为直观、可交互的感知界面，让用户能够通过调整空间和规划参数，实时预测并对比不同场景下的城市安全演变趋势。

📥 核心功能集 (Key Features)
1. 社区级空间安全监测 (GIS Spatial Monitor)
动态风险可视化：在邻里尺度（Neighborhood Scale）对高危风险（如抢劫风险）进行精细化格网渲染与动态热力叠加。

多维空间图层：集成土地利用（Zoning Layout）、建筑类型、照明设施（Lights）、绿化植被（Trees）等环境感知要素，支持图层自由切换与叠加分析。

2. 规划参数交互式微调 (Interactive Parameter Adjustment)
基于区划（Zoning-based）的协同模拟：支持对不同规划地块（如 RT-4, RS-3, B3-2 等）的控制性指标进行动态滑块调节。

空间因子干预：可实时调整容积率（FAR）、最大建筑高度（Max Height）、最小地块面积（Min Lot Area）等参数，探索空间形态改变对城市安全的潜在影响。

3. 政策文件自动化解析 (Policy File Import)
智能文本提取：支持一键上传城市规划或 ADU（附属居住单元）政策 PDF 文件。

规则映射：系统自动解析文本中的政策控制参数，并精准映射至应用的滑块控制面板，快速实现“政策文本-空间模型”的自动化桥接。

4. 24小时安全评估报告 (Automated Safety Report)
多维量化指标：自动生成包含 24 小时平均安全得分（Safety Score）、峰值风险指数（Peak Risk Index）、最危险/最安全时段的量化数据看板。

时空趋势预测：通过折线图直观展示全天候安全指数与风险等级的演变交织趋势，并精准定位 Top 5 动态风险地理坐标。

系统架构与工作流 (System Architecture & Pipeline)
应用将后端的空间地理数据处理能力与前端的智能人机交互（HCI）进行了深度整合：

[城市空间大数据 (GIS/POI/Weibo)] 
       │
       ▼
[AI / 机器学习预测模型] ─── (参数干预 / 政策解析)
       │
       ▼
[前端 HCI 移动交互界面] ─── (空间图层渲染 + 24H 动态报告)
数据与模型层：基于城市空间形态、社会经济数据及历史事件，构建高精度空间安全预测模型。

交互干预层：用户通过微调滑块或上传政策 PDF，改变模型的输入环境特征（如照明率、视线盲区比例等）。

可视化表现层：在移动端高动态渲染模拟结果，将复杂的计算框架转化为平易近人的空间设计导则与出行指南。

技术栈 (Tech Stack)
前端交互 (Frontend): React Native / Flutter (iOS & Android)

地图渲染 (GIS Engine): Mapbox GL / MapLibre / MapKit

数据处理 (Backend & Data): Python (GeoPandas, Shapely), FastAPI / Flask

设计风格 (Aesthetics): 极简主义、高对比度技术线稿、学术竞赛风数据图表

快速开始 (Quick Start)
1. 克隆仓库
Bash
git clone https://github.com/yourusername/chicago-urban-safety-app.git
cd chicago-urban-safety-app
2. 安装依赖 (以 React Native 为例)
Bash
npm install
# 或者
yarn install
3. 配置 API Keys
在项目根目录下创建一个 .env 文件，并配置你的地图与后端服务密钥：

代码段
MAPBOX_ACCESS_TOKEN=your_mapbox_token_here
BACKEND_API_URL=https://your-analysis-backend.com
4. 运行应用
Bash
# 启动 iOS 模拟器
npm run ios
# 启动 Android 模拟器
npm run android

🧭 用户使用指南 (User Guide)
本应用不仅为专业规划师提供协同设计工具，更致力于为普通居民与游客提供直观的日常出行避险决策支持。以下是核心的用户使用旅程：

1. 实时查看危险分布 (Real-Time Risk Exploration)
格子化热力图：打开应用主页，即可看到基于当前位置或特定街区的邻里尺度格网地图。地图通过颜色深度（绿/黄/红）直观渲染抢劫等犯罪风险的动态分布。

空间环境感知：用户可以一键开启“路灯（Lights）”、“绿化（Trees）”或“视线盲区（Blind）”图层，了解当前街区的空间照明与物理环境如何影响感知安全。

2. 自动化生成危险分析报告 (Generate 24H Safety Report)
动态看板：点击街区，系统将针对该区域即时生成一份《24小时安全评估报告》。

直观指标：报告包含由 AI 模型计算出的量化结果：24小时平均安全得分（Safety Score）、峰值风险指数（Peak Risk Index），以及该街区最危险与最安全的精确时段。

趋势交织图表：通过直观的红绿双线图，展示一天之中安全指数与风险等级的此消彼长。

3. 出行目的地与时间智能规划 (Smart Travel Advice)
最危险时段预警：报告会给出明确的文本 verdict（裁决提示）。例如：“夜间（20:00 - 05:00）风险显著高于白天，强烈建议在该时段采取针对性避险措施。”

动态避险导航：当用户输入目的地或规划出行路线时，应用会结合时间因子，自动避开报告中列出的 Top 5 经常性危险区域（Recurring Danger Zones），并推荐照明更好、视线更通透的替代路线。


许可证 (License)
本项目采用 MIT License 开源协议。
