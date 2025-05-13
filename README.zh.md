<div align="center">

# 🌟 Vibook — 自动维护的 Vibe Coding 项目知识库

![版本](https://img.shields.io/badge/版本-0.1.0-blue)
![支持工具](https://img.shields.io/badge/支持-Roo%20Code-brightgreen)
![许可证](https://img.shields.io/badge/许可证-MIT-orange)

<p><strong>为AI编码助手（Roo Code）提供结构化项目上下文<br>实现已有项目通过AI持续高效维护</strong></p>

[English](README.md) | [中文](README.zh.md)

</div>

---

## 📖 简介

Vibook 创建一个"AI 可理解"的知识网络，帮助 AI 编码助手（Roo Code）高效维护现有项目。

|        能力         | 实现方式               |
| :-----------------: | :--------------------- |
| 🔍 **理解项目结构** | 目录组织与关系映射     |
| 🎯 **定位关键信息** | 元数据标签与重要性标记 |
| 💡 **理解代码意图** | 上下文标记系统         |
|  🚀 **开发新功能**  | 模块实现细节文档       |
|   🛠️ **排查问题**   | 明确的文档导航路径     |

## 🚀 快速上手

1. **准备**：安装 Roo Code（推荐 Claude 3.7 Sonnet 或 Gemini 2.5 Pro）
2. **开始**：
   - 对于中小型项目：切换到 Roo Code 的`architect`模式
   - 对于大型项目：切换到 Roo Code 的`orchestrator`模式
3. **输入**：选择[中文](./ROO-PROMPT.md)或[英文](./ROO-PROMPT-EN.md)提示词
4. **配置**：回答问题设置文档系统
5. **调整**（如需）：重新执行提示词进行重新配置

> **注意**：自动文档生成将根据您的回答创建所有必要的文件和配置。

## 👀 Showcase

以下展示 Vibook 在实际项目中的应用案例，展现其自动生成文档和辅助开发的能力。

### Revas 项目案例

> [Revas](https://github.com/pinqy520/revas) 是一个用 React + CSS 在 Canvas 2D API 上 上写高性能 UI 的库，已经四年没更新了，还使用的 rollup 1.x, react-script, typescript v4，只支持 react 17。

下面视频演示了，在这个老仓库，如何通过 Vibook 自动生成文档知识库，并通过 vibe coding 完成依赖的升级和 modernization。

<table>
  <tr>
    <td align="center" >
      <strong>文档生成过程</strong>
    </td>
    <td align="center">
      <strong>使用Vibook进行开发</strong>
    </td>
  </tr>
  <tr>
    <td align="center" width="51.3%">
      <video controls width="100%" src="https://github.com/user-attachments/assets/8f2a8f80-a494-4034-a3cd-01bd6004fe4a" title="Generating Documentation"></video>
    </td>
    <td align="center" width="49.7%">
      <video controls width="100%" src="https://github.com/user-attachments/assets/1195c582-eab5-415c-9ee4-1835f894f3d9" title="Vibe Coding with Vibook"></video>
    </td>
  </tr>
</table>

## 🏗️ 系统架构

<div align="center">

```mermaid
graph TD
    classDef project stroke:#333,stroke-width:1px
    classDef docSystem stroke:#333,stroke-width:1px
    classDef aiAssist stroke:#333,stroke-width:1px
    classDef component stroke:#333,stroke-width:1px

    A((项目)):::project --> B{文档系统}:::docSystem

    subgraph 文档子系统
        B --> C1[AI索引]:::component
        B --> C2[系统架构]:::component
        B --> C3[模块文档]:::component
        B --> C4[开发指南]:::component
    end

    D[[AI助手]]:::aiAssist --> B
```

</div>

## 🔄 模式协作系统

<div align="center">

```mermaid
flowchart LR
    classDef user stroke:#333,stroke-width:1px
    classDef arch stroke:#333,stroke-width:2px,shape:hexagon
    classDef code stroke:#333,stroke-width:2px,shape:rect
    classDef test stroke:#333,stroke-width:2px,shape:diamond
    classDef summ stroke:#333,stroke-width:2px,shape:cylinder

    User((用户)):::user -->|需求| Arch[架构师]:::arch
    Arch -->|设计| Code[代码]:::code
    Code -->|完成| Test{测试}:::test
    Test -->|问题| Code
    Test -->|通过| Summary[(总结)]:::summ
    Summary -->|更新| DocSystem[文档]
```

</div>

### 模式切换

Roo 会在适当时机自动建议切换。如需手动指示：

```
"请切换到Code模式实现这个功能"
"现在切换到Test模式进行测试"
"请使用Summary模式总结这次的工作"
```

> 避免使用界面切换模式，这可能导致上下文丢失。切换时简要说明已完成工作和期望。

## 📋 生成文档

|     类别     | 内容                         |
| :----------: | :--------------------------- |
| **AI 索引**  | 系统总览、导航指南、文档标准 |
| **系统架构** | 系统结构、技术栈详情         |
| **模块文档** | 功能文档、实现细节           |
| **开发指南** | 环境设置、问题排查           |
| **配置文件** | 模式设置、规则、MCP 集成     |

---

<div align="center">

## 贡献与许可

问题和建议请通过[GitHub Issues](https://github.com/yourusername/vibook/issues)提交

**[MIT License](LICENSE)**

</div>
