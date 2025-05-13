<div align="center">

# 🌟 Vibook — The living knowledge base behind Vibe Coding

![Version](https://img.shields.io/badge/version-0.1.0-blue)
![Support](https://img.shields.io/badge/support-Roo%20Code-brightgreen)
![License](https://img.shields.io/badge/license-MIT-orange)

<p><strong>AI-friendly project documentation for<br>continuous maintenance through AI assistance (Roo Code)</strong></p>

[English](README.md) | [中文](README.zh.md)

</div>

---

## 📖 Introduction

Vibook creates an "AI-understandable" knowledge network that helps AI coding assistants (Roo Code) efficiently maintain existing projects.

|         Capability          | Implementation                                |
| :-------------------------: | :-------------------------------------------- |
| 🔍 **Understand project** | Directory organization & relationship mapping |
|  🎯 **Locate information**  | Metadata tags & importance markers            |
|  💡 **Comprehend intent**   | Contextual marking system                     |
|   🚀 **Develop features**   | Module implementation details                 |
| 🛠️ **Troubleshoot issues**  | Clear documentation navigation paths          |

## 🚀 Quick Start

1. **Prepare**: Install Roo Code with Claude 3.7 Sonnet or Gemini 2.5 Pro
2. **Start**:
   - For small to medium projects: Switch to `architect` mode in Roo Code
   - For large projects: Switch to `orchestrator` mode in Roo Code
3. **Input**: Choose [English](./ROO-PROMPT-EN.md) or [Chinese](./ROO-PROMPT.md) prompt
4. **Configure**: Answer questions to set up documentation system
5. **Adjust** (if needed): Run prompt again to reconfigure

> **Note**: Automatic documentation generation will create all necessary files and configurations based on your responses.

## 👀 Showcase

Here are practical applications of Vibook, demonstrating its capabilities for automatic documentation generation and development assistance.

### Revas Project Example

> [Revas](https://github.com/pinqy520/revas) is a high-performance UI library that uses React + CSS on the Canvas 2D API. It hasn't been updated for four years and still uses outdated dependencies: rollup 1.x, react-script, typescript v4, and only supports React 17.

The videos below demonstrate how to use Vibook to automatically generate a documentation knowledge base for this legacy repository and perform dependency upgrades and modernization through vibe coding.

<table>
  <tr>
    <td align="center">
      <strong>Documentation Generation</strong>
    </td>
    <td align="center">
      <strong>Development with Vibook</strong>
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

## 🏗️ System Architecture

<div align="center">

```mermaid
graph TD
    classDef project stroke:#333,stroke-width:1px
    classDef docSystem stroke:#333,stroke-width:1px
    classDef aiAssist stroke:#333,stroke-width:1px
    classDef component stroke:#333,stroke-width:1px

    A((Project)):::project --> B{Doc System}:::docSystem

    subgraph Documentation Subsystem
        B --> C1[AI Index]:::component
        B --> C2[Architecture]:::component
        B --> C3[Module Docs]:::component
        B --> C4[Dev Guides]:::component
    end

    D[[AI Assistant]]:::aiAssist --> B
```

</div>

## 🔄 Mode Collaboration System

<div align="center">

```mermaid
flowchart LR
    classDef user stroke:#333,stroke-width:1px
    classDef arch stroke:#333,stroke-width:2px,shape:hexagon
    classDef code stroke:#333,stroke-width:2px,shape:rect
    classDef test stroke:#333,stroke-width:2px,shape:diamond
    classDef summ stroke:#333,stroke-width:2px,shape:cylinder

    User((User)):::user -->|Requirements| Arch[Architect]:::arch
    Arch -->|Design| Code[Code]:::code
    Code -->|Complete| Test{Test}:::test
    Test -->|Issues| Code
    Test -->|Pass| Summary[(Summary)]:::summ
    Summary -->|Update| DocSystem[Docs]
```

</div>

### Mode Switching

Roo automatically suggests switching at appropriate times. If needed, manually direct:

```
"Please switch to Code mode to implement this feature"
"Now switch to Test mode to test our implementation"
"Please use Summary mode to document this work"
```

> Avoid UI mode switching as it may lose context. Include brief explanations when switching.

## 📋 Generated Documentation

|     Category      | Contents                                                    |
| :---------------: | :---------------------------------------------------------- |
|   **AI Index**    | System overview, navigation guides, documentation standards |
| **Architecture**  | System structure, tech stack details                        |
|    **Modules**    | Functional documentation, implementation details            |
|    **Guides**     | Setup instructions, troubleshooting procedures              |
| **Configuration** | Mode settings, rules, MCP integration                       |

---

<div align="center">

## Contribution & License

Issues and suggestions via [GitHub Issues](https://github.com/yourusername/vibook/issues)

**[MIT License](LICENSE)**

</div>
