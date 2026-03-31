---
name: nova-graph
description: >
  使用 Nova Graph 模板构建星云类地球仪产品。当用户想新增一个 Nexus 产品、
  或基于地球仪+星云图+详情卡结构构建任何数据可视化项目时使用此 skill。
  关键词触发：nexus、nova graph、地球仪、星云图、力导向图、人物关系图、
  文明探索、新闻地球、新增产品、复用模板。
---

# Nova Graph Skill

## 这是什么

Nova Graph 是一套单文件 HTML 模板，所有 Nexus 产品都基于它构建。
模板文件位于 `nexus/nova-template.html`。

**三层结构（不可更改）：**
```
🌍 地球仪  →（点击国家）→  ✨ 星云图  →（点击节点）→  🃏 详情卡
```

---

## 新建产品的步骤

1. 复制 `nova-template.html`，重命名为 `index.html`
2. 搜索 `[CUSTOMIZE]`，共 5 处需要修改
3. 放入 `nexus/<新产品文件夹>/` 下
4. 在根目录 `README.md` 加一行入口链接

---

## 5 处必改内容

### 1. 产品标题
```html
<title>[CUSTOMIZE: 产品名称]</title>
```
同时改 `STRINGS` 里的 `tb-tagline` 和 `sidebar-title`。

### 2. DATA — 数据节点
每个国家/地区的结构：
```javascript
{
  id:   "唯一id",          // 对应 POLYS 里的 id
  zh:   "中文名",
  en:   "English name",
  f:    "🏳️",             // 旗帜 emoji
  la:   纬度,
  lo:   经度,
  cont: { zh:"洲", en:"Region" },
  p: [  // 该地区下的节点
    {
      e:    "English Key",  // 唯一标识，作为节点 ID
      n:    "中文名",
      s:    "分类key",      // 对应 CAT_COLORS 的 key
      role: { zh:"角色", en:"Role" },
      bio:  { zh:"简介", en:"Bio" },
      extra:"附加信息",     // 可选，显示在卡片副标题
      sk:   ["标签"],       // 可选
      link1:"https://...", // 可选，详情卡主链接
      link2:"https://...", // 可选，详情卡次链接
      link3:"https://...", // 可选
    }
  ]
}
```

### 3. RELS — 节点关系
```javascript
// type 只有三种：supply（绿色箭头）/ compete（红色虚线）/ partner（紫色虚线）
{ a:"English Key A", b:"English Key B", type:"supply", zh:"供应", en:"Supply" }
```
`a` 和 `b` 必须与节点的 `e` 字段完全一致。

### 4. CAT_COLORS / CAT_NAMES — 分类颜色
```javascript
const CAT_COLORS = {
  tech: "#7dd3fc",   // 分类key: 十六进制颜色
  // 添加你的分类...
};
const CAT_NAMES = {
  en: { tech: "Tech" },
  zh: { tech: "科技" },
};
```

### 5. STRINGS — 界面文案
```javascript
const STRINGS = {
  en: { "tb-tagline": "YOUR PRODUCT NAME", ... },
  zh: { "tb-tagline": "你的产品名", ... },
};
```

---

## 图片规则

只用真实照片。推荐图源（境内境外均可访问）：
- `images.unsplash.com/photo-XXXXX?w=300&q=80`
- `upload.wikimedia.org`

---

## 链接规则

每个节点详情卡建议提供双链接：
- `link1` → 全球用户（Wikipedia、Forbes 等）
- `link2` → 国内用户（百度百科、官方中文媒体等）

---

## 不需要改的部分

以下代码在所有产品中完全一致，**不要修改**：
- 地球仪渲染引擎（`drawGlobe`）
- 星云物理模拟（`buildGraphData` / `drawGraph`）
- 音频引擎（`startA` / `scheduleAmbient`）
- 语言切换逻辑（`toggleLang` / `applyStrings`）
- 星空背景（stars IIFE）

---

## 添加新国家轮廓

如果 `POLYS` 里没有你需要的国家，按此格式添加：
```javascript
{ id:"country_id", pts:[[纬度,经度], [纬度,经度], ...] }
```
`id` 必须与 `DATA` 中对应国家的 `id` 一致。

---

## 添加到 Nexus Repo

```
nexus/
├── README.md          ← 加一行新产品的入口
├── Business/
│   └── index.html
├── Civilization/
│   └── index.html
└── <新产品>/          ← 新建文件夹，放入 index.html
    └── index.html
```

访问地址：`https://chen0126y.github.io/nexus/<新产品>/`
