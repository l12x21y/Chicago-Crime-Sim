# Chicago-Crime-Sim

Chicago-Crime-Sim 是一款专为居民、游客以及城市规划师设计的社区尺度空间安全监测与交互式模拟移动应用。项目打破了传统静态地图的限制，将复杂的城市大数据与机器学习模型（AI Modeling）转化为直观、可交互的感知界面，让用户能够通过调整空间和规划参数，实时预测并对比不同场景下的城市安全演变趋势。

核心功能集 (Key Features)
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
许可证 (License)
本项目采用 MIT License 开源协议。
