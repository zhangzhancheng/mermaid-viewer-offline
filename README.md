# Mermaid Viewer 离线版使用指南

## 📁 文件夹结构

```
mermaid-viewer-offline/
├── index.html          # 主页面（推荐使用）
├── README.md           # 使用说明
├── css/                # 样式文件（已下载）
├── js/                 # JavaScript 文件（已下载）
└── html/               # 其他 HTML 页面（已下载）
```

## 🚀 快速开始

### 方式 1：使用简化的离线编辑器（推荐）

1. **直接打开** `index.html` 文件
2. 该版本使用 CDN 加载 Mermaid 库，如果网络可用即可使用
3. 如果网络不可用，需要手动下载 Mermaid 库（见下方"完全离线方案"）

### 方式 2：使用下载的完整网站

1. 打开 `html/zh` 或 `html/zh_d2_0` 等文件
2. 这些是从 mermaid-viewer.com 下载的页面
3. 部分功能可能依赖在线资源

## 📝 功能说明

### 支持的图表类型

1. **流程图 (Flowchart)**
   ```mermaid
   graph TD
       A[开始] --> B{判断}
       B -->|是 | C[操作 1]
       B -->|否 | D[操作 2]
   ```

2. **时序图 (Sequence Diagram)**
   ```mermaid
   sequenceDiagram
       Alice->>John: 你好 John，最近怎么样？
       John-->>Alice: 很好！
   ```

3. **类图 (Class Diagram)**
   ```mermaid
   classDiagram
       Animal <|-- Duck
       Animal <|-- Fish
       Animal: +int age
       Animal: +String gender
   ```

4. **状态图 (State Diagram)**
   ```mermaid
   stateDiagram-v2
       [*] --> Still
       Still --> [*]
       Still --> Moving
       Moving --> Still
   ```

5. **甘特图 (Gantt Chart)**
   ```mermaid
   gantt
       title 项目计划
       dateFormat  YYYY-MM-DD
       section 阶段 1
       任务 1 :2024-01-01, 30d
   ```

6. **思维导图 (Mindmap)**
   ```mermaid
   mindmap
       root((主题))
           分支 1
               子分支 1
               子分支 2
   ```

## 🔧 完全离线方案

如果要完全离线使用（不依赖任何网络连接），需要：

### 步骤 1：下载 Mermaid 库

访问以下地址下载 mermaid.min.js：
```
https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.min.js
```

保存到 `mermaid-viewer-offline/js/` 目录

### 步骤 2：修改 index.html

找到这一行：
```html
<script src="https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.min.js"></script>
```

改为：
```html
<script src="js/mermaid.min.js"></script>
```

### 步骤 3：打开使用

直接双击 `index.html` 即可完全离线使用

## 💡 使用技巧

1. **实时预览**：在编辑器中输入 Mermaid 代码，1 秒后自动渲染
2. **加载示例**：点击"加载示例"按钮查看示例代码
3. **导出图片**：支持导出 SVG 和 PNG 格式
4. **语法高亮**：建议使用支持 Mermaid 语法的编辑器（如 VS Code）

## ⚠️ 注意事项

1. **网络依赖**：简化版 index.html 默认从 CDN 加载 Mermaid 库
2. **浏览器兼容**：推荐使用 Chrome、Edge、Firefox 等现代浏览器
3. **文件下载**：如果某些资源加载失败，请检查浏览器控制台
4. **版本更新**：下载的是特定版本的资源，可能不是最新版

## 📚 学习资源

- [Mermaid 官方文档](https://mermaid.js.org/)
- [Mermaid 中文教程](https://mermaid.nodeee.cn/)
- [Mermaid Live Editor](https://mermaid.live/)

## 🆘 故障排除

### 问题 1：打开页面显示空白
**解决**：检查浏览器控制台是否有错误，确保 JavaScript 已启用

### 问题 2：图表无法渲染
**解决**：
1. 检查 Mermaid 代码语法是否正确
2. 确认 Mermaid 库已正确加载
3. 查看浏览器控制台的错误信息

### 问题 3：导出功能不可用
**解决**：确保图表已成功渲染，并且浏览器支持 Blob 和 URL 对象

## 📞 技术支持

如有问题，请参考：
- Mermaid GitHub: https://github.com/mermaid-js/mermaid
- 原网站：https://mermaid-viewer.com/zh

---

**最后更新**: 2024 年
**版本**: 1.0
