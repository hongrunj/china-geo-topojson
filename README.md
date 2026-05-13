# china-geo-topojson

中国行政区 TopoJSON 数据（省/市/县三级），用于 Power BI Deneb 视觉的地图渲染。

## 文件说明

| 文件 | 层级 | 要素数 | 大小 |
|---|---|---|---|
| `(20260512)china_province.labeled.topo.json` | 省级 | 34 | ~48KB |
| `(20260512)china_city.labeled.topo.json` | 地级市 | 275 | ~163KB |
| `(20260512)china_county.labeled.topo.json` | 区县 | 577 | ~310KB |

每个要素的 `properties` 含：
- `adcode`：行政区划代码（与 Power BI 数据表 join 用）
- `cp`：`[lon, lat]` 中心点坐标（用于标签定位）

## 使用方式

在 Vega/Vega-Lite spec 中按 URL 加载：

```json
{
  "url": "https://gitee.com/<用户名>/<仓库名>/raw/master/(20260512)china_province.labeled.topo.json",
  "format": {"type": "topojson", "feature": "temp_prov"}
}
```

`feature` 字段名（即 TopoJSON 的 object key）：
- 省级：`temp_prov`
- 市级：`temp`
- 县级：`china_county`
