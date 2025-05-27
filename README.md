# AI-Powered Agent Optimizer for Microsoft Copilot Studio

**Automated YAML Optimization & Best Practice Enforcement using GitHub Copilot**

This repository provides specialized AI prompts that automatically optimize and improve your Microsoft Copilot Studio `.mcs.yml` files based on official Microsoft best practices. Each prompt is crafted for specific component types and designed to work seamlessly with **Visual Studio Code + Copilot Studio Extensions** and **GitHub Copilot** (works with GPT-4o, Claude Sonnet, and other available AI models) for intelligent, context-aware optimization.

## 📋 Available Prompts

### 1. 📝 [System Topics](./SystemTopics_BestPractices.md)
**Use for:** Fallback, Greeting, Goodbye, ConversationStart, EndofConversation, etc.
- System trigger configuration
- Conversation flow logic
- User experience design
- Error handling patterns

### 2. 🎯 [Triggers & Intent Recognition](./Triggers_BestPractices.md)
**Use for:** Topic trigger phrases and intent configuration
- Trigger phrase optimization (5-10 varied phrases)
- Natural language understanding
- Topic overlap prevention
- Intent recognition effectiveness

### 3. 💬 [Regular Topics](./RegularTopics_BestPractices.md)
**Use for:** Custom business logic topics
- Topic structure and organization
- Conversational design
- Entity usage and slot filling
- Integration with other components

### 4. 🧠 [Knowledge & Search](./Knowledge_BestPractices.md)
**Use for:** Search.mcs.yml and knowledge integration
- SearchAndSummarizeContent configuration
- Knowledge source integration
- Response quality optimization
- Performance considerations

### 5. ⚙️ [Actions & Power Automate](./Actions_BestPractices.md)
**Use for:** External service integrations and automations
- Connection configuration
- Input/output mapping
- Error handling and security
- User experience during execution

### 6. 🌐 [Bot Settings & Configuration](./BotSettings_BestPractices.md)
**Use for:** settings.mcs.yml and bot-level configuration
- Authentication and security
- AI settings optimization
- Feature enablement
- Performance configuration

### 7. 🔄 [Conversation Management](./ConversationManagement_BestPractices.md)
**Use for:** StartOver, Reset, state management topics
- User confirmation flows
- State management
- Variable cleanup
- Dialog control

### 8. 🤖 [Agent Configuration](./AgentConfiguration_BestPractices.md)
**Use for:** agent.mcs.yml and GPT agent behavior configuration
- Agent instructions and behavior
- Conversation starters optimization
- GPT capabilities configuration
- Agent personality and tone

### 9. 🏷️ [Entities & Data Types](./Entities_BestPractices.md)
**Use for:** entities/*.mcs.yml and data type definitions
- Entity type selection and configuration
- Value definitions and synonyms
- Smart matching optimization
- Slot filling integration

## 🚀 How to Use These Prompts

### Intended Workflow with Visual Studio Code + GitHub Copilot

These prompts are designed to be used with the **Copilot Studio Extensions** in **Visual Studio Code** along with **GitHub Copilot** to automatically analyze and improve your Microsoft Copilot Studio YAML files based on official best practices.

#### Recommended Setup:
1. **Visual Studio Code** with Copilot Studio Extensions installed
2. **GitHub Copilot** with your preferred AI model (GPT-4o, Claude Sonnet, etc.)
3. **Open your Copilot Studio project** containing .mcs.yml files

#### Usage Steps:
1. **Open the relevant YAML file** in VS Code (e.g., `Fallback.mcs.yml`, `agent.mcs.yml`)
2. **Copy the appropriate prompt** from the component-specific file
3. **Use GitHub Copilot Chat** with the prompt
4. **Paste or reference your YAML content** in the chat
5. **Review the AI-generated improvements** that follow Microsoft best practices
6. **Apply suggested changes** directly in VS Code with Copilot's assistance

#### Example Workflow:
```
1. Open Fallback.mcs.yml in VS Code
2. Copy prompt from SystemTopics_BestPractices.md
3. In Copilot Chat: 
   "[paste prompt]
   
   Please analyze this YAML file: [select and reference the file]"
4. Review AI suggestions for improvements
5. Apply changes with Copilot's code assistance
```

### Alternative: Direct GitHub Copilot Chat Usage:
1. **Copy the prompt** from the relevant component file
2. **Paste your YAML file** after the prompt
3. **Submit to Copilot Chat** for analysis
4. **Review suggestions** and apply improvements manually

## 🎯 Why Use These Prompts with VS Code + GitHub Copilot?

### **Intelligent Code Analysis**
- **Context-aware suggestions** - AI models understand your entire project structure and relationships between YAML files
- **Real-time validation** - Get immediate feedback on best practice compliance while editing
- **Pattern recognition** - AI identifies common anti-patterns and suggests proven solutions

### **Seamless Development Experience**
- **In-editor assistance** - No need to switch between tools or copy/paste between applications
- **Project-aware recommendations** - Suggestions consider your specific bot configuration and existing topics
- **Automated improvements** - AI can directly suggest code changes with proper YAML formatting

### **Best Practice Enforcement**
- **Microsoft-aligned guidance** - All prompts based on official Microsoft Learn documentation
- **Consistent quality** - Ensure all team members follow the same standards
- **Continuous improvement** - Regular analysis helps maintain code quality over time

## 📚 Based on Official Microsoft Guidelines

All prompts are created based on official Microsoft Learn documentation:
- [Topic Authoring Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/topic-authoring-best-practices)
- [Trigger Phrases Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/trigger-phrases-best-practices)
- [Fallback Topic Guidelines](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/fallback-topic)
- [System Topics](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-system-topics)
- [Configuration Fundamentals](https://learn.microsoft.com/en-us/microsoft-copilot-studio/configuration-fundamentals)

## ⚠️ Important Notes

- **Integrate with VS Code workflow** - Use these prompts within your existing Copilot Studio development environment
- **Leverage AI assistance** - GitHub Copilot's AI models provide context-aware suggestions based on your project structure
- **Preserve YAML structure** - Prompts focus on improvements within existing framework
- **Maintain IDs and references** - Keep topic and action connections intact
- **Follow security guidelines** - Ensure proper authentication and access control
- **Test changes thoroughly** - Validate improvements in test environment first
- **Use VS Code extensions** - Take advantage of YAML validation and Copilot Studio tooling

## 🔧 Component Quick Reference

| Component Type | File Pattern | Prompt File |
|---|---|---|
| System Topics | `Fallback.mcs.yml`, `Greeting.mcs.yml` | [SystemTopics_BestPractices.md](./SystemTopics_BestPractices.md) |
| Regular Topics | `EnquireAbout*.mcs.yml`, custom topics | [RegularTopics_BestPractices.md](./RegularTopics_BestPractices.md) |
| Knowledge | `Search.mcs.yml` | [Knowledge_BestPractices.md](./Knowledge_BestPractices.md) |
| Actions | `actions/*.mcs.yml` | [Actions_BestPractices.md](./Actions_BestPractices.md) |
| Settings | `settings.mcs.yml` | [BotSettings_BestPractices.md](./BotSettings_BestPractices.md) |
| Conversation Mgmt | `StartOver.mcs.yml`, `ResetConversation.mcs.yml` | [ConversationManagement_BestPractices.md](./ConversationManagement_BestPractices.md) |
| Agent Config | `agent.mcs.yml` | [AgentConfiguration_BestPractices.md](./AgentConfiguration_BestPractices.md) |
| Entities | `entities/*.mcs.yml` | [Entities_BestPractices.md](./Entities_BestPractices.md) |

Each prompt is standalone and can be used independently for focused component analysis and improvement.
