# 12-地标型 · 1871年前后巴黎鸟瞰地标图

## 1. 原始案例图片

![1871年前后巴黎鸟瞰地标图](https://commons.wikimedia.org/wiki/Special:FilePath/Pictorial_map_of_the_city_of_Paris_and_its_environs.jpg)

[原始发布页及授权](https://commons.wikimedia.org/wiki/File:Pictorial_map_of_the_city_of_Paris_and_its_environs.jpg)；作者：Harper & Brothers；授权：公有领域。未修改原图。

## 2. 定义与特征

以可辨识地点或建筑作为视觉锚点，建立地点、名称与空间位置的关联。 地标名称来自作品页分类，非地图逐字转录；连线表示目录归属，不表示实际道路。

## 3. 原始资料摘录与数据清洗

以下为发布说明支持的结构抽样及明确标记的研究者分析项，非完整原图转录。

| 原始描述或分析项 | 规范标签 | 类型 |
|---|---|---|
| Palais du Louvre | Palais du Louvre | 宫殿 |
| Notre-Dame de Paris | Notre-Dame de Paris | 宗教建筑 |
| Arc de Triomphe | Arc de Triomphe | 纪念建筑 |
| Jardin des Tuileries | Jardin des Tuileries | 园林 |

清洗规则：去首尾空白，统一文本类型，保留标签语义；id 为新建本地键。缺失坐标、流量或数量保留为空，不补造。地标名称来自作品页分类，非地图逐字转录；连线表示目录归属，不表示实际道路。

## 4. 清洗后数据集

| id | label | type |
|---:|---|---|
| 1 | Palais du Louvre | 宫殿 |
| 2 | Notre-Dame de Paris | 宗教建筑 |
| 3 | Arc de Triomphe | 纪念建筑 |
| 4 | Jardin des Tuileries | 园林 |

数据字典：id（整数，本地唯一键）；label（文本，地标名称或分析项）；type（分类文本，研究者归类）。类别与空间位置可作为后续扩展字段，未知量值不填零。

## 5. 数据结构

```mermaid
flowchart TD
 R[地标] --> I[id]
 R --> L[label]
 R --> T[type]
 R -.扩展.-> E[空间位置]
```

## 6. 字段组合与统计

label + type 用于区分对象；id + label 用于索引；扩展关系字段用于组织对象联系。此次抽样为 4 条，不能代表原作对象总数。定性数据无需强行使用均值或占比。

## 7. 基础图形与统计图形

```mermaid
flowchart TD
 R[巴黎地标] --- A[卢浮宫]
 R --- B[巴黎圣母院]
 R --- C[凯旋门]
 R --- D[杜乐丽花园]
```

地标名称来自作品页分类，非地图逐字转录；连线表示目录归属，不表示实际道路。 此图为研究分析示意，不是等比例地图或数量流图。RAWGraphs 推荐：有真实经纬度时采用点地图或区域地图；地理位置不可用普通类别排序替代。

## 8. 视觉编码映射图

```mermaid
flowchart LR
 L[label] --> A[文字标签]
 T[type] --> B[类别符号或分组]
 E[空间位置] --> C[空间定位或对应标记]
```

## 9. 叙事结构

```mermaid
flowchart LR
 A[明确阅读目标] --> B[识别地标]
 B --> C[理解空间位置]
 C --> D[形成整体认识]
```

## 10. 设计总结与限制

以可辨识地点或建筑作为视觉锚点，建立地点、名称与空间位置的关联。 原图链接已查到公开发布记录；当前为定性分析，未完成全图逐项校对及 GitHub 实际渲染验证。
