# Agent Configuration Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio agent configuration YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-ai-features and agent configuration guidelines.

⚠️ CRITICAL YAML FORMATTING: 
- PRESERVE the exact indentation and formatting when providing corrected YAML
- YAML is indentation-sensitive and incorrect spacing will break the file structure
- Use exactly 2 spaces for each indentation level consistently
- NEVER use tabs - only spaces
- Maintain proper alignment for all nested elements
- DO NOT modify structural elements like `kind:`, `name:`, `instructions:` - these are framework-required
- DO NOT change line breaks or combine separate YAML properties on the same line

🚨 STRUCTURAL PRESERVATION FOR AGENT CONFIG:
- Keep agent framework properties (`kind:`, `name:`, `instructions:`, `conversationStarters:`) exactly as they are
- Preserve all agent configuration structure (language, capabilities, etc.)
- Only modify content within instruction text and conversation starter messages
- Never merge separate YAML properties onto the same line

🎯 MINIMAL CHANGES ONLY: Only suggest changes that:
- Fix clear violations of Microsoft's official best practices
- Address significant security, performance, or functionality issues
- Have substantial impact on user experience or bot effectiveness
- Are explicitly recommended in official Microsoft documentation

🚫 AVOID:
- Adding unnecessary complexity to agent configurations
- Creative additions that weren't in the original agent setup
- Over-engineering basic agent functionality
- Adding advanced features unless explicitly needed
- Modifying agent YAML structure elements (kind, name, instructions, conversationStarters)
- Changing indentation of existing properly formatted YAML
- Combining separate YAML properties on the same line

✅ FOCUS ON:
1. Agent instruction clarity fixes
2. Basic conversation starter improvements
3. Essential GPT capability corrections
4. Critical YAML syntax errors

⚠️ AGENT CONFIG YAML STRUCTURE WARNING: NEVER modify these framework elements:
- `kind:` properties (keep exactly as is)
- `name:` (must be on separate line)
- `instructions:` structure
- `conversationStarters:` properties
- Do NOT combine properties like "kind: name:" - this breaks YAML
5. Basic agent personality setting corrections

KEEP IT SIMPLE: Most agent configurations should maintain their core functionality unless there are clear violations to fix.
```

## Component-Specific Guidelines

### ✅ Agent Configuration Checklist
- [ ] Clear, specific agent instructions defined
- [ ] Appropriate agent personality and tone set
- [ ] 3-5 varied conversation starters provided
- [ ] Basic safety guidelines included
- [ ] Task-specific behaviors clearly outlined
- [ ] GPT capabilities appropriately configured
- [ ] Correct YAML structure and formatting
- [ ] Agent name and description are descriptive

### 🎯 Essential Configuration Areas

**Agent Instructions:**
- Clear purpose and role definition
- Basic behavioral guidelines
- Task-oriented instruction organization
- Communication style and tone requirements

**Conversation Starters:**
- 3-5 diverse starter topics
- User-friendly and engaging prompts
- Representative of bot capabilities
- Clear and actionable language

**GPT Capabilities:**
- Appropriate feature enablement
- Basic configuration settings
- Integration with bot knowledge

## ⚠️ YAML Formatting Critical
- Use exactly 2 spaces for each indentation level
- Never use tabs - only spaces
- Maintain consistent alignment for all nested elements
- Preserve original indentation structure when making improvements

### 📚 Reference Guidelines
- [Agent Configuration Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-ai-features)
- [Conversation Starters](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/conversation-starters)
