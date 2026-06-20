# VGI 公众举报平台 - Web GIS 课程作业 (3.5.1)

## 📋 作业要求

创建一个允许公众报告嫌犯信息的 Web 应用（VGI - Volunteered Geographic Information）。

执法部门通常会鼓励公众举报嫌疑犯，为了扩大举报途径，他们希望搭建一个 GIS 应用，市民可以通过该应用报告四名极为危险的嫌疑犯，并上传这些嫌疑犯的照片或视频。

### 基本要求
- ✅ 该应用程序可在智能手机上运行（响应式设计）
- ✅ 允许公民上传照片和视频
- ✅ 包含举报模板，每个模板代表一个嫌犯，便于公众举报
- ✅ 使用 Leaflet + 高德地图底图展示地图和嫌犯位置

### CSV/GeoJSON 数据字段
- `Suspect_Name` / `Suspect_Number`
- `Description`：描述嫌犯在做什么以及看到嫌犯的地点
- `Long` / `Lat`
- `Date_Saw_Suspect`
- `Report_Date`
- `Reported_By`
- `User_Phone`

## 📁 文件结构

```
第二个作业/
├── index.html          # 主应用页面 (HTML + CSS + JavaScript)
├── suspects.csv        # 嫌犯数据文件 (CSV格式)
├── suspects.geojson    # 嫌犯要素数据 (GeoJSON格式，可作为要素图层URL提交)
└── README.md           # 本说明文件
```

## 🚀 部署到 GitHub Pages（获取提交URL）

### 第一步：创建 GitHub 仓库

1. 打开 [GitHub.com](https://github.com) 并登录
2. 点击 **New repository**（新建仓库）
3. 仓库名随意，如 `webgis-vgi-report`
4. 设置为 **Public**（公开）
5. 点击 **Create repository**

### 第二步：上传文件

```bash
# 在本地初始化仓库
git init
git add .
git commit -m "提交VGI举报平台"

# 关联远程仓库
git remote add origin https://github.com/你的用户名/webgis-vgi-report.git
git branch -M main
git push -u origin main
```

或者直接在 GitHub 网页上点击 **Add file → Upload files**，将 `第二个作业` 目录下的文件拖入上传。

### 第三步：开启 GitHub Pages

1. 进入仓库 → **Settings** → **Pages**
2. **Branch** 选 `main`，**文件夹** 选 `/root`
3. 点击 **Save**
4. 等待 1-2 分钟，获得 URL：`https://你的用户名.github.io/webgis-vgi-report/`

## 📄 提交内容填写

| 提交项 | 填写内容 |
|--------|---------|
| **(1) 要素图层的 REST URL** | `https://你的用户名.github.io/webgis-vgi-report/suspects.geojson` |
| **(2) Web 应用的 URL** | `https://你的用户名.github.io/webgis-vgi-report/index.html` |

## 🎯 功能特性

- 🗺️ **交互式地图**：Leaflet + 高德地图底图，嫌犯位置展示
- 🕵️ **嫌犯信息卡**：展示 4 名嫌犯的详细信息，点击跳转地图
- 📝 **举报表单**：包含所有 CSV 字段的标准化举报模板，嫌犯预填
- 📸 **照片/视频上传**：支持多文件上传和即时预览
- 📍 **坐标拾取**：点击地图自动获取坐标 + GPS定位
- 📋 **举报记录**：本地保存举报历史（localStorage）
- 📱 **响应式设计**：完美适配手机和电脑

## 🛠️ 技术栈

- [Leaflet](https://leafletjs.com/) + 高德地图底图 — 轻量级地图引擎
- 纯 HTML/CSS/JavaScript — 无需任何框架
- FileReader API — 图片/视频上传预览
- localStorage — 本地数据持久化
- GeoJSON — 要素图层数据格式

## 📚 数据说明

`suspects.geojson` 可作为要素图层 REST URL 提交，包含 4 名嫌犯：
1. **SUS-001** 张某某 - 男性，35岁，市中心商业区附近
2. **SUS-002** 李某某 - 男性，28岁，学校周边区域
3. **SUS-003** 王某某 - 女性，40岁，多个商场
4. **SUS-004** 赵某某 - 男性，45岁，公园和老年人活动区域
