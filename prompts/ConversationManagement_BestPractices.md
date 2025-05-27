# Conversation Management Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio conversation management topic YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-system-topics and conversation flow guidelines.

⚠️ CRITICAL YAML FORMATTING: 
- PRESERVE the exact indentation and formatting when providing corrected YAML
- YAML is indentation-sensitive and incorrect spacing will break the file structure
- Use exactly 2 spaces for each indentation level consistently
- NEVER use tabs - only spaces
- Maintain proper alignment for all nested elements
- DO NOT modify structural elements like `kind:`, `beginDialog:`, `actions:` - these are framework-required
- DO NOT change line breaks or combine separate YAML properties on the same line

🚨 STRUCTURAL PRESERVATION FOR CONVERSATION TOPICS:
- Keep topic framework properties (`kind:`, `beginDialog:`, `actions:`, `id:`) exactly as they are
- Preserve all conversation flow structure (OnRecognizedIntent, conditions, etc.)
- Only modify content within prompts, messages, and condition values
- Never merge separate YAML properties onto the same line

🎯 MINIMAL CHANGES ONLY: Only suggest changes that:
- Fix clear violations of Microsoft's official best practices
- Address significant security, performance, or functionality issues
- Have substantial impact on user experience or bot effectiveness
- Are explicitly recommended in official Microsoft documentation

🚫 AVOID:
- Adding unnecessary complexity to conversation management
- Creative additions that weren't in the original topic
- Over-engineering basic conversation flow functionality
- Adding advanced features unless explicitly needed
- Modifying conversation YAML structure elements (kind, beginDialog, actions, id)
- Changing indentation of existing properly formatted YAML
- Combining separate YAML properties on the same line

✅ FOCUS ON:
1. User confirmation flow fixes
2. Basic conversation state corrections
3. Essential variable cleanup improvements
4. Critical YAML syntax errors

⚠️ CONVERSATION YAML STRUCTURE WARNING: NEVER modify these framework elements:
- `id: main` (keep exactly as is, on separate line)
- `kind:` properties
- `beginDialog:` structure
- `actions:` (must be on separate line)
- Do NOT combine properties like "id: main beginDialog:" - this breaks YAML
5. Basic user messaging improvements

KEEP IT SIMPLE: Most conversation management topics should maintain their core functionality unless there are clear violations to fix.
```

## Component-Specific Guidelines

### ✅ Conversation Management Checklist
- [ ] Clear user confirmation flows implemented
- [ ] Basic conversation state management
- [ ] Variable cleanup procedures defined
- [ ] User-friendly prompts and messaging
- [ ] Essential error handling
- [ ] Appropriate start behavior configuration
- [ ] Correct YAML structure and formatting

### 🎯 Essential Management Areas

**State Management:**
- Basic conversation variable handling
- Proper variable initialization and cleanup
- Context preservation during topic switches

**User Experience:**
- Clear confirmation flows and prompts
- User-friendly messaging and tone
- Basic error handling and recovery

**Dialog Control:**
- Appropriate start behavior configuration
- Essential conversation outcome tracking
- Basic integration with system topics

### 📚 Reference Guidelines
- [Conversation Management Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-system-topics)
- [System Topics](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-system-topics)

## ⚠️ YAML Formatting Critical
- Use exactly 2 spaces for each indentation level
- Never use tabs - only spaces
- Maintain consistent alignment for all nested elements
- Preserve original indentation structure when making improvements

### 📚 Reference Guidelines
- [System Topics](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-system-topics)
- [Variable Management](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-variables)
- [Conversation Design](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/topic-authoring-best-practices)
