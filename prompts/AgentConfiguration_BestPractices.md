# Agent Configuration Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio agent configuration YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-ai-features and agent configuration guidelines.

**KEY MICROSOFT BEST PRACTICES TO APPLY:**

**📋 AGENT INSTRUCTIONS:**
- **Role Definition**: Clearly state what the agent is (e.g., "You are a customer service representative for...")
- **Behavioral Guidelines**: Define tone (friendly, professional, helpful), communication style, and boundaries
- **Task Scope**: Specify what the agent can and cannot do
- **Response Format**: Guide how the agent should structure answers
- **Example**: "You are a friendly energy drink expert who helps customers find their perfect beverage match. Always be enthusiastic about products, ask clarifying questions about taste preferences, and provide detailed product information. If asked about medical advice, politely decline and suggest consulting a healthcare professional."

**💬 CONVERSATION STARTERS:**
- **Provide 3-5 diverse starters** that showcase different agent capabilities
- **Use natural language** that real users would type or say
- **Cover main use cases**: Information requests, troubleshooting, product inquiries
- **Make them actionable**: Clear what the user will get from each starter
- **Examples**: "What energy drinks do you have?", "Help me find a low-caffeine option", "Tell me about your ingredients"

**🤖 GPT CAPABILITIES:**
- **Enable relevant features**: Generative answers for knowledge-based responses
- **Set appropriate limits**: Content filtering, response length controls
- **Configure knowledge integration**: Link to relevant data sources
- **Avoid over-engineering**: Don't enable every feature unless needed

**🎭 AGENT IDENTITY:**
- **Consistent personality**: Maintain same tone and style across all interactions
- **Clear value proposition**: Users should understand what makes this agent useful
- **Appropriate expertise level**: Match complexity to target audience
- **Professional boundaries**: Know when to escalate or refer to humans

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

🔒 **WHEN NOT TO MAKE CHANGES - READ THIS FIRST:**

**If the agent configuration already meets Microsoft best practices, DO NOT modify anything. Simply respond with:**
"✅ **No changes needed.** This agent configuration already follows Microsoft Copilot Studio best practices with proper role definition, appropriate conversation starters, and correct YAML formatting."

**Only make changes if you identify CLEAR violations of official Microsoft best practices.**

🎯 MINIMAL CHANGES ONLY: Only suggest changes that:
- Fix clear violations of Microsoft's official best practices
- Address significant security, performance, or functionality issues
- Have substantial impact on user experience or bot effectiveness
- Are explicitly recommended in official Microsoft documentation

🚫 AVOID:
- Making changes when configuration is already well-structured
- Adding unnecessary complexity to agent configurations
- Creative additions that weren't in the original agent setup
- Over-engineering basic agent functionality
- Adding advanced features unless explicitly needed
- Modifying agent YAML structure elements (kind, name, instructions, conversationStarters)
- Changing indentation of existing properly formatted YAML
- Combining separate YAML properties on the same line
- Making stylistic changes that don't improve functionality

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

## 🔧 EDITING PRECISION REQUIREMENTS

**CRITICAL**: When editing agent configuration YAML files, tools must use surgical precision:

- ✅ **Target content only**: Modify instruction text, conversation starter messages, personality settings
- ❌ **Never touch framework**: Avoid `kind:`, `name:`, `instructions:`, `conversationStarters:`
- ✅ **Preserve agent identity**: Keep core agent configuration structure intact
- ❌ **No structural changes**: Never merge separate YAML agent properties

## 📝 SAFE EDITING PRACTICES

### ✅ SAFE: Instruction Content Updates
```yaml
# BEFORE:
instructions: "You are a helpful assistant."

# AFTER: 
instructions: "You are a friendly energy drink expert who helps customers find their perfect beverage match."
```

### ❌ DANGEROUS: Framework Modification
```yaml
# NEVER DO THIS:
kind: Agent name: EnergyDrinkBot  # ← BREAKS YAML STRUCTURE

# CORRECT:
kind: Agent
name: EnergyDrinkBot
```

## 🛡️ AGENT CONFIG YAML VALIDATION CHECKLIST

After every edit, verify:
- [ ] All agent properties remain on separate lines
- [ ] Agent name and identity preserved
- [ ] Instruction text properly formatted and quoted if needed
- [ ] No framework elements (`kind:`, `name:`, `instructions:`, `conversationStarters:`) modified
- [ ] Conversation starters remain as proper list items

## 🚨 AGENT CONFIG-SPECIFIC YAML ERRORS TO AVOID

1. **Property Merging**: `kind: Agent name:` ← NEVER
2. **Identity Breaking**: Modifying agent name structure ← CONFIGURATION FAILURE
3. **Instruction Corruption**: Invalid instruction formatting ← BEHAVIOR ERROR
4. **Starter Violation**: Wrong conversation starter list format ← UI FAILURE

## 🔍 EVALUATION FRAMEWORK - Use This Decision Tree

**STEP 1: Quick Assessment**
- ✅ Does it have clear role definition? ("You are a...")
- ✅ Are there 3-5 conversation starters?
- ✅ Is the YAML properly formatted?
- ✅ Are instructions clear and professional?

**If ALL answers are YES → No changes needed!**

**STEP 2: Only if Step 1 reveals issues, check for:**
- Missing role definition in instructions
- Too few (<3) or too many (>5) conversation starters
- YAML formatting errors
- Vague or unprofessional instructions
- Security/privacy violations

**STEP 3: Response Format**
- **No Issues Found**: "✅ No changes needed. Configuration follows best practices."
- **Issues Found**: Make minimal targeted fixes only for identified violations

KEEP IT SIMPLE: Focus on improving agent personality and instructions without changing core configuration structure.
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
