#Nexus SKILL.md
What is Nexus? / 这是什么？
EN — Nexus is a collection of interactive globe products. Each product shares the same structure but explores a different topic.
中文 — Nexus 是一组互动地球仪产品。每个产品结构相同，但主题不同。

Current Products / 当前产品
Folder / 文件夹Product / 产品名Topic / 主题Business/NEXUS全球商业精英关系图Civilization/Echoes of Civilization世界历史文明探索
Live URL / 访问地址：https://chen0126y.github.io/nexus/<文件夹名>/

How Every Product Works / 每个产品的结构
All products use the same 3-step navigation. / 所有产品都是同一套三层交互：
🌍 地球仪 Globe
      ↓ 点击国家 Click a country
✨ 星云图 Nebula  （节点网络 / node network）
      ↓ 点击节点 Click a node
🃏 详情卡 Card  （介绍 + 链接 / info + links）
What changes between products / 每个产品不同的地方：

The data (people, places, news…) / 数据内容（人物、遗迹、新闻…）
The colors and music / 颜色和音乐
The card fields / 详情卡的字段

What never changes / 永远不变的部分：

The globe engine / 地球仪引擎
The nebula physics / 星云物理动画
The audio system / 音频系统
The EN/中 language toggle / 中英切换


Adding a New Product / 如何新增一个产品

在 GitHub 新建文件夹 — 例如 News/ 或 Film/
复制最接近主题的现有 index.html 作为起点
替换数据 — 清空原有内容，填入新主题的节点和关系
调整颜色和文案 — 改主题色、标题、加载语句
在根目录 README.md 加一行 — 注明新产品名称和链接


不需要改地球仪、星云、音频这三部分代码。
No need to touch the globe, nebula, or audio code.


Image Rule / 图片规则
EN — Use real photos only. Preferred sources (work in China + globally):

images.unsplash.com (add ?w=300&q=80 at the end)
upload.wikimedia.org

中文 — 只用真实照片，不用 AI 生成图。推荐图源（境内境外都能加载）：

images.unsplash.com（末尾加 ?w=300&q=80）
upload.wikimedia.org


Link Rule / 链接规则
EN — Every card should have two links: one for global users, one for China.
中文 — 每张详情卡都要提供两个链接：一个全球，一个国内。
Global / 全球China / 国内Wikipedia百度百科Forbes官方中文媒体UNESCO国家文物局等
