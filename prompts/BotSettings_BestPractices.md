# Bot Settings & Configuration Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio bot settings YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/configuration-fundamentals and bot configuration guidelines.

⚠️ CRITICAL YAML FORMATTING: 
- PRESERVE the exact indentation and formatting when providing corrected YAML
- YAML is indentation-sensitive and incorrect spacing will break the file structure
- Use exactly 2 spaces for each indentation level consistently
- NEVER use tabs - only spaces
- Maintain proper alignment for all nested elements
- DO NOT modify structural elements like `kind:`, `settings:`, `authentication:` - these are framework-required
- DO NOT change line breaks or combine separate YAML properties on the same line

🚨 STRUCTURAL PRESERVATION FOR BOT SETTINGS:
- Keep settings framework properties (`kind:`, `settings:`, `authentication:`, `aiFeatures:`) exactly as they are
- Preserve all bot configuration structure (language, security, features)
- Only modify content within setting values and configuration parameters
- Never merge separate YAML properties onto the same line

🎯 MINIMAL CHANGES ONLY: Only suggest changes that:
- Fix clear violations of Microsoft's official best practices
- Address significant security, performance, or functionality issues
- Have substantial impact on user experience or bot effectiveness
- Are explicitly recommended in official Microsoft documentation

🚫 AVOID:
- Adding unnecessary complexity to bot settings
- Creative additions that weren't in the original configuration
- Over-engineering basic bot functionality
- Adding advanced features unless explicitly needed
- Modifying bot settings YAML structure elements (kind, settings, authentication, aiFeatures)
- Changing indentation of existing properly formatted YAML
- Combining separate YAML properties on the same line

✅ FOCUS ON:
1. Authentication configuration fixes
2. Basic AI and GPT setting corrections
3. Essential feature enablement adjustments
4. Critical YAML syntax errors

⚠️ BOT SETTINGS YAML STRUCTURE WARNING: NEVER modify these framework elements:
- `kind:` properties (keep exactly as is)
- `settings:` (must be on separate line)
- `authentication:` structure
- `aiFeatures:` properties
- Do NOT combine properties like "kind: settings:" - this breaks YAML
5. Basic security setting corrections

KEEP IT SIMPLE: Most bot settings should maintain their core functionality unless there are clear violations to fix.
```

## Component-Specific Guidelines

### ✅ Bot Settings & Configuration Checklist
- [ ] Authentication mode appropriate for use case
- [ ] Access control policy properly configured
- [ ] AI settings optimized for bot functionality
- [ ] Essential features enabled (GenerativeActions, SemanticSearch)
- [ ] Recognizer type matches bot requirements
- [ ] Basic security settings configured
- [ ] Template version is current and supported
- [ ] Correct YAML structure and formatting

### 🎯 Essential Configuration Areas

**Authentication & Security:**
- Authentication mode selection (None, Integrated, Manual)
- Access control policy assignment
- Basic security considerations

**AI Settings:**
- GPT settings optimization for bot functionality
- Generative actions enablement when needed
- Semantic search configuration
- Recognizer type selection

**Feature Configuration:**
- Essential feature enablement
- Template version management
- Language and localization basics

### 📚 Reference Guidelines
- [Bot Configuration Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/configuration-fundamentals)
- [Security Settings](https://learn.microsoft.com/en-us/microsoft-copilot-studio/configuration-security)

**AI & GPT Settings:**
- useModelKnowledge optimization
- File analysis enablement
- Semantic search configuration
- Latest models opt-in consideration
- Generative AI recognizer setup
- Knowledge integration settings

**Feature Configuration:**
- GenerativeActionsEnabled for advanced AI features
- Knowledge source integration
- External service connections
- Performance optimization features
- Analytics and monitoring capabilities

## ⚠️ YAML Formatting Critical
- Use exactly 2 spaces for each indentation level
- Never use tabs - only spaces
- Maintain consistent alignment for all nested elements
- Preserve original indentation structure when making improvements

### 📚 Reference Guidelines
- [Bot Configuration Fundamentals](https://learn.microsoft.com/en-us/microsoft-copilot-studio/configuration-fundamentals)
- [Security Overview](https://learn.microsoft.com/en-us/microsoft-copilot-studio/security-overview)
- [AI Features Configuration](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-ai-features)
