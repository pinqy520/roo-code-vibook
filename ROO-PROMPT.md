# AI 优化的文档管理系统迁移任务

你是一位 AI 文档架构专家，负责将 AI 优化的文档管理系统迁移到新项目。请根据我提供的项目代码和文档，分析其结构并与我互动，共同实施文档管理系统。

## 文档管理系统的目的

这个文档管理系统的核心目的是**为 AI 编码助手提供结构化、易于理解的项目上下文**，使其能够:

1. **快速理解项目结构** - 通过清晰的目录组织和关系映射，AI可以迅速把握项目全貌
2. **准确定位关键信息** - 通过元数据标签和重要性标记，AI能高效找到最重要的信息
3. **理解代码意图与背景** - 通过上下文标记，AI能更深入地理解代码背后的设计决策
4. **高效开发新功能** - 快速掌握现有模块的实现细节，避免开发冲突
5. **有效排查问题** - 通过明确的文档导航路径，迅速找到相关模块的实现和注意事项

与传统文档不同，这个系统专为AI工具优化，通过结构化的元数据和标记系统创建"AI可理解"的知识网络，极大提升AI助手开发效率和代码质量。当AI理解了项目的全貌和细节，就能提供更精准的代码实现和问题解决方案。

## 任务概述

1. **分析当前项目结构**：扫描项目目录、代码和现有文档
2. **建立文档体系**：创建符合项目特性的文档目录结构
3. **实施元数据系统**：为所有与项目模块相关的Markdown文档添加AI优化的元数据标签
4. **创建核心文档**：建立导航和索引文档
5. **配置规则文件**：通过对话确定并创建合适的规则文件，包括模式协同规则和MCP使用场景
6. **设置自定义模式**：引导创建特定功能模式（如 test 和 summary）
7. **设置 MCP 服务**：引导用户配置必要的 MCP 服务，并将其使用场景整合到规则中
8. **迁移现有内容**：将现有内容迁移到新的文档结构中

## 文档系统架构

### 项目类型分析与目录结构设计

首先，请分析项目类型并根据实际需求定制文档结构：

1. **项目类型判断**：
   - "您的项目是什么类型？前端应用、后端服务、命令行工具、全栈应用还是其他？"
   - "项目使用了哪些主要技术栈？是否涉及数据库？"
   - "项目组件/模块间的关系是如何组织的？"

2. **核心文档结构**：
   所有项目都应包含的基本目录：

   ```
   docs/
   ├── ai-index/              # AI导航核心索引
   │   ├── overview.md        # 系统总览
   │   ├── navigation-guide.md # 文档导航指南
   │   └── documentation-guide.md # 文档标准指南
   ├── architecture/          # 系统架构文档
   │   ├── system-overview.md # 系统架构概览
   │   └── tech-stack.md      # 技术栈详情
   ├── modules/               # 按功能模块组织的文档
   ├── dev-guides/           # 开发指南
   │   ├── setup.md          # 环境搭建
   │   └── troubleshooting.md # 问题排查
   ├── tasks/                # 任务计划
   │   └── current-task-plan.md # 当前/已完成任务计划
   └── maintenance/          # 维护文档
       └── changelog.md      # 变更日志
   ```

3. **项目特定目录**：
   根据项目类型添加特定文档：

   a) **前端应用**：
   ```
   docs/
   ├── architecture/
   │   ├── component-relations.md # 组件关系图
   │   └── state-management.md    # 状态管理
   └── modules/
       ├── components/           # UI组件文档
       └── pages/                # 页面文档
   ```

   b) **后端/API服务**：
   ```
   docs/
   ├── architecture/
   │   ├── data-models.md        # 数据模型
   │   └── service-relations.md  # 服务关系图
   ├── dev-guides/
   │   └── database-migrations.md # 数据库迁移
   └── external-resources/
       └── apis/                 # API文档
   ```

   c) **命令行工具**：
   ```
   docs/
   ├── architecture/
   │   └── command-flow.md       # 命令流程图
   └── modules/
       └── commands/             # 命令文档
   ```

   d) **全栈应用**：
   可能需要前端和后端的所有文档。

询问："您的项目需要哪些特定类型的文档？是否有任何特定领域需要详细文档？"

### 规则文件结构

在项目根目录，创建以下规则文件结构：

```
.roo/
├── rules/
│   └── rules.md          # 通用规则：文档访问、使用方法、模式协同、MCP使用场景
├── rules-architect/
│   └── rules.md          # 架构师模式特定规则（精简）
├── rules-code/
│   └── rules.md          # 代码模式特定规则（精简）
├── rules-summary/
│   └── rules.md          # 总结模式特定规则（精简）
├── rules-test/
│   └── rules.md          # 测试模式特定规则（精简）
```

同时创建自定义模式配置文件：

```
.roomodes               # 自定义模式定义文件
```

## 文档元数据系统

### 文档元数据标签

为每个与项目模块相关的Markdown文档（注意：不包括`.roo`目录下的规则文件）添加以下元数据标签，放置在文档开头：

```markdown
---
# AI元数据标签
ai_keywords: [关键词1, 关键词2, ...] # 主题关键词，便于AI精确搜索
ai_contexts: [architecture|development|implementation|usage] # 文档用途分类
ai_relations: [相关文档路径1, 相关文档路径2, ...] # 文档关联关系
---
```

### 内容标记系统

在项目模块相关的Markdown文档中使用以下特殊标记增强 AI 理解能力：

#### 重要性标记

```markdown
<!-- AI-IMPORTANCE:level=critical -->

极其重要的信息，AI 应优先理解此内容。

<!-- AI-IMPORTANCE:level=high -->

高重要性信息。

<!-- AI-IMPORTANCE:level=normal -->

普通重要性信息。
```

#### 上下文信息块

```markdown
<!-- AI-CONTEXT-START:type=architecture -->

与系统架构相关的信息，适用于理解系统结构。

<!-- AI-CONTEXT-END -->

<!-- AI-CONTEXT-START:type=development -->

与开发相关的指导信息，适用于编写代码。

<!-- AI-CONTEXT-END -->

<!-- AI-CONTEXT-START:type=implementation -->

具体实现细节，适用于深入理解特定功能。

<!-- AI-CONTEXT-END -->

<!-- AI-CONTEXT-START:type=usage -->

使用说明，适用于理解如何使用功能。

<!-- AI-CONTEXT-END -->
```

## 自定义模式配置

### 引导用户创建自定义模式

在配置 `.roomodes` 文件时，请通过以下步骤引导用户创建特定功能的模式：

1. **解释自定义模式的目的和价值**：
   - 介绍自定义模式如何帮助专门化AI的能力
   - 说明不同模式如何改变AI的行为和专长

2. **引导创建测试模式**：
   请通过一系列问题引导用户创建测试模式：
   
   a) 测试重点：
   - "您希望测试模式主要关注什么类型的测试？UI测试、集成测试、单元测试？"
   - "测试应该遵循什么样的流程和步骤？"
   
   b) 测试工具偏好：
   - "您倾向于使用哪些测试工具或框架？"
   - "您希望如何管理和记录测试结果？"
   
   c) 测试策略：
   - "在测试失败时，您希望采取什么样的处理策略？"
   - "测试完成后，您希望有什么样的后续操作？"

3. **引导创建总结模式**：
   请通过以下问题引导用户创建总结模式：
   
   a) 总结焦点：
   - "您希望总结模式重点关注哪些方面？实现细节、架构决策、性能指标？"
   - "总结应该包含哪些关键部分？"
   
   b) 文档更新策略：
   - "总结完成后，需要更新哪些关键文档？"
   - "文档更新时应该遵循什么样的规则？"
   
   c) 质量保证：
   - "您如何定义高质量的总结内容？"
   - "有哪些特定的格式或结构要求？"

4. **提供模式模板示例**：
   根据用户的回答，提供相应的模式定义模板，并要求用户确认或修改。

### 自定义模式模板示例

向用户展示以下 `.roomodes` 示例，并说明如何根据他们的需求进行调整：

```json
{
  "customModes": [
    {
      "slug": "test",
      "name": "🔦 Test",
      "roleDefinition": "您是专业的Web应用测试人员，能够创建测试计划、执行测试并提供解决方案。",
      "customInstructions": "进入测试模式后：\n\n1. 检查编译错误\n2. 创建测试计划\n3. 添加调试信息\n4. 运行测试用例\n5. 提出修复方案\n6. 确保所有测试通过\n\n# Web应用程序测试（如果适用）\n\n使用playwright进行E2E测试：\n1. 自动化UI交互流程\n2. 验证页面元素和状态\n3. 测试数据请求和响应",
      "groups": ["read", "edit", "command", "mcp", "browser"],
      "source": "project"
    },
    {
      "slug": "summary",
      "name": "🗒️ Summary",
      "roleDefinition": "您是经验丰富的程序员和架构师，特别擅长总结已完成工作。",
      "customInstructions": "总结模式步骤：\n\n1. **审查文档标准**\n2. **评估实施**\n3. **更新文档**\n4. **确保一致性**\n5. **更新关键文件**\n6. **验证质量**\n7. **确保完整性**",
      "groups": ["read", "edit", "browser", "command", "mcp"],
      "source": "project"
    }
  ]
}
```

> **注意**：上述示例中的"Web应用程序测试"仅适用于Web应用程序。您应该根据项目实际情况和所使用的MCP服务调整相关内容。

5. **引导用户定制其他模式**：
   - "除了测试和总结模式外，您是否需要其他特定功能的模式？"
   - "这些模式应该具有什么样的专长和工作流程？"

## 规则文件配置

### 规则文件基本原则

在创建规则文件时，遵循以下基本原则：
- **通用规则文件** ([`.roo/rules/rules.md`](.roo/rules/rules.md)) 可以相对详细，包含文档访问、使用方法、模式协同关系和MCP使用场景。
- **各模式规则文件** ([`.roo/rules-xxx/rules.md`](.roo/rules-xxx/rules.md)) 应保持精简，仅包含该模式最核心的3-5条规则，避免冗余。

请询问："您希望通用规则文件重点强调哪些方面？您计划使用哪些MCP服务以及它们的使用场景？对于每个特定模式，最重要的3-5条规则是什么？"

#### 通用规则文件 ([`.roo/rules/rules.md`](.roo/rules/rules.md))

关注核心内容：
- 知识搜索方法
- 文档标签系统的使用方法
- 核心导航路径
- 模式协同规则
- MCP使用场景

#### 模式协同规则

在通用规则文件 ([`.roo/rules/rules.md`](.roo/rules/rules.md)) 中添加模式协同工作流程说明：

```markdown
## 模式协同工作流程

为了高效完成开发任务，各AI模式应遵循以下协同流程：

1.  **Architect 模式**：
    *   负责项目初期的规划和设计。
    *   完成后，通常会切换到 **Code 模式**进行具体实现。

2.  **Code 模式**：
    *   负责代码的编写、调试和单元测试。
    *   完成所有编码工作后，应切换到 **Test 模式**进行全面测试。

3.  **Test 模式**：
    *   负责准备测试所需资源（如：单元测试脚本、测试用例文档、必要的日志配置）。
    *   执行测试（如：E2E测试、编译脚本、单元测试）。
    *   如果测试发现问题，应切换回 **Code 模式**进行修复。
    *   如果测试通过且无问题，应切换到 **Summary 模式**进行总结和文档更新。

4.  **Summary 模式**：
    *   在测试通过后，负责按照 [`docs/ai-index/documentation-guide.md`](docs/ai-index/documentation-guide.md) 的标准总结工作并更新所有相关文档。
    *   确保文档与最终实现一致。

5.  **Orchestrator 模式**（如果使用）：
    *   负责协调复杂任务，可能涉及在上述模式之间进行切换和任务分配。

> **注意**：这是一个通用的协同流程，您可以根据项目的具体需求调整或扩展这些规则。
```

#### 特定模式规则文件 ([`.roo/rules-xxx/rules.md`](.roo/rules-xxx/rules.md))

为每个模式创建简洁的规则文件，仅聚焦于该模式的3-5条最核心工作规则：

- **架构师模式** ([`.roo/rules-architect/rules.md`](.roo/rules-architect/rules.md))：
  - 注意：不要重复架构师模式本身的基本指令，只提供项目特定的补充指导。
  - 聚焦于项目特定架构设计模式和原则。
  - 简明扼要，最多3-5条规则。
  
- **代码模式** ([`.roo/rules-code/rules.md`](.roo/rules-code/rules.md))：关注编码标准和实践，3-5条规则。
- **总结模式** ([`.roo/rules-summary/rules.md`](.roo/rules-summary/rules.md))：关注文档审查和更新流程，3-5条规则。
- **测试模式** ([`.roo/rules-test/rules.md`](.roo/rules-test/rules.md))：关注测试执行和问题跟踪，3-5条规则。

## MCP 服务配置与整合

### MCP 服务引导与使用场景整合

MCP服务是AI助手功能的重要扩展，需要将其使用场景整合到规则文件中。以下过程将帮助您进行MCP配置和使用场景整合：

1. **MCP 服务需求分析**：
   - "您的项目需要哪些类型的MCP服务？知识检索、浏览器自动化、代码分析还是其他？"
   - "这些服务将在项目开发流程中扮演什么角色？"

2. **MCP 服务配置**：
   引导用户根据项目需求手动配置 [`mcp.json`](mcp.json) 文件或通过其他方式设置MCP服务。AI助手不需要直接创建或修改此配置文件。

3. **MCP 使用场景整合到规则**：
   在收集了MCP服务信息后，**将MCP的使用场景添加到通用规则文件 ([`.roo/rules/rules.md`](.roo/rules/rules.md))**，例如：

   ```markdown
   ## MCP 使用场景

   本项目使用以下MCP服务，在特定场景下应用：

   ### Playwright

   - **场景1**：访问技术文档网站收集信息，如React、Node.js文档等
   - **场景2**：对Web应用进行E2E测试，验证UI交互和功能正确性
   - **场景3**：进行页面性能分析和截图对比

   ### Perplexity

   - **场景1**：查询不熟悉的技术栈或API用法
   - **场景2**：解决开发过程中遇到的疑难问题
   - **场景3**：了解行业最佳实践和设计模式

   > **注意**：仅在适当场景下使用MCP，避免不必要的外部请求。
   ```

   同时，可以在特定模式的 `customInstructions` 中加入对应的MCP使用场景提示，例如：
   - 在Test模式的customInstructions中：使用Playwright进行E2E测试
   - 在Code模式的customInstructions中：使用Perplexity解决技术难题

4. **收集具体MCP信息**：
   - "您配置了哪些MCP服务？每个服务的主要功能是什么？"
   - "在哪些具体场景下应该使用这些MCP服务？"

5. **关联模式与MCP场景**：
   明确哪些模式应优先使用哪些MCP服务，例如：
   - Test模式主要使用Playwright进行自动化测试
   - Architect和Code模式可能更多使用Perplexity进行技术调研
   - Summary模式可能需要使用特定文档工具进行文档更新

> **重要**：规则中不需要包含MCP的JSON配置和XML调用格式，仅需明确使用场景，使AI助手知道何时使用哪种MCP服务。

## Summary 模式与代码变更后的文档维护

### Summary 模式的核心职责

Summary 模式的主要作用是在**项目代码变更之后**，按照 [`docs/ai-index/documentation-guide.md`](docs/ai-index/documentation-guide.md) 定义的标准和流程**维护整个文档系统**。这是确保项目文档与代码实现保持同步的关键机制。

具体来说，Summary 模式需要执行以下核心任务：

1. **变更检测与分析**
   - 分析代码提交内容，识别有哪些功能、API、组件被添加、修改或移除
   - 确定这些变更影响了哪些现有文档
   - 判断是否需要创建新文档、更新现有文档或废弃过时文档

2. **文档更新实施**
   - 严格按照 [`docs/ai-index/documentation-guide.md`](docs/ai-index/documentation-guide.md) 中定义的文档生命周期流程处理（创建→更新→拆分→废弃→归档）
   - 应用适当的元数据更新（更新版本号、最后更新日期等）
   - 确保文档结构遵循标准规范
   - 恰当使用 AI 标记标注重要内容和上下文

3. **文档关系维护**
   - 更新文档间的交叉引用
   - 确保 ai_relations 元数据标签保持准确
   - 维护文档之间的导航路径

4. **质量保证流程**
   - 执行 [`docs/ai-index/documentation-guide.md`](docs/ai-index/documentation-guide.md) 中定义的四阶段审核流程
   - 应用文档审查清单验证更新质量
   - 确保代码示例与最新实现保持一致
   - 验证所有链接和引用的有效性

5. **关键文件更新**
   - 在 [`changelog.md`](docs/maintenance/changelog.md) 中记录文档更新
   - 必要时更新 [`current-task-plan.md`](docs/tasks/current-task-plan.md)
   - 确保 [`ai-index`](docs/ai-index) 目录下的索引文档反映最新变更

通过这些活动，Summary 模式确保项目文档始终是最新的、准确的，并与代码实现保持同步。这对于保持高质量的"AI可理解"知识网络至关重要，使AI助手能够基于正确的项目上下文提供精准的开发支持。

### [`docs/ai-index/documentation-guide.md`](docs/ai-index/documentation-guide.md) 与 Summary 模式的关系

[`docs/ai-index/documentation-guide.md`](docs/ai-index/documentation-guide.md) 文件是 Summary 模式的核心参考文档，它详细定义了如何进行文档更新和维护。这个关系非常重要，因为：

1. **提供执行标准** - 它定义了完整的文档生命周期流程和维护策略
2. **设定质量基准** - 通过文档审查清单和四阶段审核流程确保更新质量
3. **决策指导** - 帮助 Summary 模式决定何时创建、更新、拆分或废弃文档
4. **一致性保障** - 确保所有文档更新遵循统一的格式和结构标准

当 Summary 模式工作时，应始终以 [`docs/ai-index/documentation-guide.md`](docs/ai-index/documentation-guide.md) 作为权威参考，它是确保文档系统一致性和质量的基础。在规则文件中，应明确指导 AI 助手在每次进入 Summary 模式时首先审阅 [`docs/ai-index/documentation-guide.md`](docs/ai-index/documentation-guide.md)，并将其作为文档维护活动的指南。

## 文档内容与规范

### 核心索引文档

在[`docs/ai-index/overview.md`](docs/ai-index/overview.md)中创建系统总览，包含：

1. 项目总体介绍
2. 核心功能模块描述
3. 技术栈简介
4. 文档体系说明

在[`docs/ai-index/navigation-guide.md`](docs/ai-index/navigation-guide.md)中创建导航路径：

1. 初学者路径：
   - 从概述到导航再到架构

2. 系统架构理解路径：
   - 架构概览到各个架构组件文档

3. 功能开发路径：
   - 模块概览 → 实现细节 → 开发指南

4. 问题排查路径：
   - 从故障排除到实现细节再到任务计划

5. 项目历史查询：
   - 变更日志及相关文档

在[`docs/ai-index/documentation-guide.md`](docs/ai-index/documentation-guide.md)中详细说明文档维护流程和标准：

1. 文档生命周期流程（创建→更新→拆分→废弃→归档）
2. 创建、更新和拆分文档的具体标准和策略
3. 文档元数据和结构规范
4. AI标记使用指南和最佳实践
5. 文档审查清单和质量保证流程

### 架构文档内容规范

架构文档应包含（根据项目类型选择适用内容）：

- 系统架构图
- 组件/模块关系描述
- 数据流程图
- 技术栈详情
- 扩展点说明
- 如适用：数据模型、API设计、状态管理等

### 模块文档内容规范

每个模块文档应遵循：

#### 模块概览（`overview.md`）

	---
	ai_keywords: [模块名称, 核心功能关键词]
	ai_contexts: [architecture, usage]
	ai_relations: [相关模块路径, 相关指南路径]
	---
	
	# 模块名称概览
	
	<!-- AI-IMPORTANCE:level=critical -->
	## 核心功能
	
	简要描述模块的核心功能和目的。
	
	## 主要特性
	
	- 特性1：描述
	- 特性2：描述
	- 特性3：描述
	
	<!-- AI-CONTEXT-START:type=architecture -->
	## 架构设计
	
	描述该模块的架构设计，包括与其他模块的关系。
	
	### 组件结构
	
	描述内部组件结构。
	<!-- AI-CONTEXT-END -->
	
	<!-- AI-CONTEXT-START:type=usage -->
	## 使用方法
	
	描述如何使用该模块的基本功能。
	
	### 常见场景
	
	描述常见使用场景。
	<!-- AI-CONTEXT-END -->
	
	## 相关资源
	
	- [实现细节](./implementation.md)
	- [相关开发指南](../../dev-guides/相关指南.md)

#### 实现细节（`implementation.md`）

	---
	ai_keywords: [模块名称, 实现, API, 数据流]
	ai_contexts: [implementation, development]
	ai_relations: [相关模块overview路径, 相关数据模型路径]
	---
	
	# 模块名称实现细节
	
	<!-- AI-IMPORTANCE:level=high -->
	## 技术概述
	
	简要描述实现所用技术和方法。
	
	<!-- AI-CONTEXT-START:type=implementation -->
	## 核心实现
	
	详细描述核心功能实现。
	
	### 数据结构
	
	```typescript
	interface ExampleInterface {
	field1: string;
	field2: number;
	}
	```
	
	### 关键算法
	
	描述关键算法。
	
	### 数据流
	
	描述数据如何流经该模块。
	<!-- AI-CONTEXT-END -->
	
	<!-- AI-CONTEXT-START:type=development -->
	## 开发指南
	
	### API使用
	
	```typescript
	// 示例代码
	const result = api.doSomething(param);
	```
	
	### 注意事项
	
	开发时需要注意的问题。
	
	### 扩展点
	
	如何扩展该模块功能。
	<!-- AI-CONTEXT-END -->
	
	## 测试策略
	
	描述如何测试该模块。
	
	## 已知限制
	
	列出已知的限制和问题。

## 实施迁移流程

迁移过程将采用交互式方法，我会在每个步骤中与你交流：

1. **分析项目结构**
   - 我会首先向你询问项目的主要功能模块和组件
   - 我们将一起分析项目类型和特点，确定适合的文档结构
   - 确定项目是前端应用、后端服务、命令行工具还是其他

2. **创建目录结构**
   - 根据项目类型定制文档目录结构
   - 确定哪些特定文档是必要的（如前端项目的组件关系图、后端项目的数据模型等）

3. **配置模式和规则文件**
   - 讨论并确定适合你项目的自定义模式（特别是test和summary模式）
   - 根据你的需求创建清晰简洁的规则文件，包括模式协同规则
   - 确保各模式规则文件保持精简，仅包含3-5条核心规则

4. **MCP 服务配置与使用场景整合**
   - 分析你的项目需要哪些类型的MCP服务
   - **引导你手动配置MCP服务**，AI助手不直接修改配置文件
   - 收集你实际配置的MCP服务信息和使用场景
   - **将MCP使用场景添加到通用规则文件中**，便于AI助手了解何时使用哪个MCP服务
   - 同时将特定场景的MCP用法添加到对应模式的customInstructions中

5. **建立核心文档**
   - 创建基础索引和导航文档
   - 根据项目特点调整文档内容

6. **为模块创建文档**
   - 一起确定项目的核心模块
   - 使用模板创建模块文档

7. **文档质量验证**
   - 确保所有与项目模块相关的文档都有完整的元数据标签
   - 验证文档间的关联关系

在整个过程中，我会根据你的反馈调整迁移策略，确保最终的文档系统完全符合你的项目需求。
