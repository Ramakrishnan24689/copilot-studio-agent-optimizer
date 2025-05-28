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

🔒 **WHEN NOT TO MAKE CHANGES - READ THIS FIRST:**

**If the conversation management configuration already meets Microsoft best practices, DO NOT modify anything. Simply respond with:**
"✅ **No changes needed.** This conversation management configuration already follows Microsoft Copilot Studio best practices with proper conversation flow, user confirmation, and correct YAML formatting."

**Only make changes if you identify CLEAR violations of official Microsoft best practices.**

🎯 MINIMAL CHANGES ONLY: Only suggest changes that:
- Fix clear violations of Microsoft's official best practices
- Address significant security, performance, or functionality issues
- Have substantial impact on user experience or bot effectiveness
- Are explicitly recommended in official Microsoft documentation

🚫 AVOID:
- Making changes when configuration is already well-structured
- Adding unnecessary complexity to conversation management
- Creative additions that weren't in the original topic
- Over-engineering basic conversation flow functionality
- Adding advanced features unless explicitly needed
- Modifying conversation YAML structure elements (kind, beginDialog, actions, id)
- Changing indentation of existing properly formatted YAML
- Combining separate YAML properties on the same line
- Making stylistic changes that don't improve functionality

## 🔍 EVALUATION FRAMEWORK - Use This Decision Tree

**STEP 1: Quick Assessment**
- ✅ Are conversation flows logical and user-friendly?
- ✅ Are user confirmations and state management proper?
- ✅ Is the YAML properly formatted?
- ✅ Are variable handling and cleanup appropriate?

**If ALL answers are YES → No changes needed!**

**STEP 2: Only if Step 1 reveals issues, check for:**
- Poor conversation flow or user experience
- Missing user confirmations where needed
- YAML formatting errors
- Inappropriate variable handling

**STEP 3: Response Format**
- **No Issues Found**: "✅ No changes needed. Configuration follows best practices."
- **Issues Found**: Make minimal targeted fixes only for identified violations

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

## 🔧 EDITING PRECISION REQUIREMENTS

**CRITICAL**: When editing conversation management YAML files, tools must use surgical precision:

- ✅ **Target content only**: Modify prompts, messages, condition values, variable names
- ❌ **Never touch framework**: Avoid `kind:`, `beginDialog:`, `actions:`, `id:`
- ✅ **Preserve flow logic**: Keep conversation state and branching intact
- ❌ **No structural changes**: Never merge separate YAML properties

## 📝 SAFE EDITING PRACTICES

### ✅ SAFE: Message Content Updates
```yaml
# BEFORE:
activity: "Okay, I'll help you with that."

# AFTER: 
activity: "Great! I'll help you with that right away."
```

### ❌ DANGEROUS: Framework Modification
```yaml
# NEVER DO THIS:
id: main actions: [...]  # ← BREAKS YAML STRUCTURE

# CORRECT:
id: main
actions:
  - kind: SendMessage
```

## 🛡️ CONVERSATION YAML VALIDATION CHECKLIST

After every edit, verify:
- [ ] All conversation flow elements remain properly structured
- [ ] No framework properties (`kind:`, `beginDialog:`, `actions:`, `id:`) were modified
- [ ] Variable references and conditions still valid
- [ ] User input handling logic preserved
- [ ] Indentation follows 2-space standard consistently

## 🚨 CONVERSATION-SPECIFIC YAML ERRORS TO AVOID

1. **Action Merging**: `actions: kind: SendMessage` ← NEVER
2. **Condition Breaking**: Modifying condition structure ← FLOW FAILURE
3. **Variable Corruption**: Changing variable reference format ← RUNTIME ERROR
4. **Dialog Nesting**: Improper beginDialog modifications ← STRUCTURAL FAILURE
```

## Component-Specific Guidelines

### 🏗️ SYSTEM TOPICS FUNDAMENTALS *(Source: [Microsoft Learn - System Topics](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-system-topics))*

**Built-in System Topics:**
- Automatically added to every agent - cannot be deleted
- Essential for common system events and conversation management
- Can be disabled if not needed, but recommend keeping core topics active
- Customization recommended only after mastering end-to-end conversation design

**Manual Triggering:**
- System topics can be manually triggered via redirection
- Some system topics have customizable trigger phrases
- Use redirection to call system topics from custom topics when appropriate

### 🎯 CORE SYSTEM TOPIC BEHAVIORS *(Source: [Microsoft Learn - System Topics](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-system-topics))*

**Conversation Start:**
- Greets users and introduces agent capabilities
- Automatically triggers when agent first engages with user
- Critical first impression - ensure welcoming and informative

**Fallback Topic:**
- Informs users when query couldn't be matched to any topic
- Triggers when agent can't match user's question/message
- Opportunity to guide users or escalate appropriately

**Multiple Topics Matched:**
- Prompts users to choose intended topic when multiple topics match closely
- Sets system variable to identify triggered topic
- Reduces conversation confusion and improves user experience

### 🔄 CONVERSATION FLOW MANAGEMENT *(Source: [Microsoft Learn - System Topics](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-system-topics))*

**End of Conversation:**
- Confirms customer query is answered
- Must be triggered via redirection from custom topics
- Proper conversation closure improves user satisfaction

**Reset Conversation:**
- Clears all variable values and forces latest published content
- Triggered via redirection when conversation restart needed
- Useful for complex scenarios requiring fresh conversation state

**Escalate Topic:**
- Informs customers about human agent handoff
- Triggers on "talk to agent" match or Escalate system event
- Critical for Omnichannel integrations - follow specific handoff instructions

### ⚠️ ERROR HANDLING & DEBUGGING *(Source: [Microsoft Learn - System Topics](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-system-topics))*

**On Error Topic:**
- Provides error code, conversation ID, and timestamp for debugging
- Shows detailed error messages in Test agent pane for authors
- Essential for troubleshooting conversation issues
- Automatically triggers when errors occur during conversation

**Authentication Integration:**
- Sign in topic prompts customers when user authentication enabled
- Triggers at conversation start when sign-in required
- Also triggers when conversation reaches nodes using authentication variables

### 🎛️ CONVERSATIONAL BOOSTING *(Source: [Microsoft Learn - System Topics](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-system-topics))*

**Generative Answers:**
- Creates responses from external data sources
- Triggers when agent can't find topic match for user query
- Enables knowledge-based fallback without custom topic authoring
- Integrates with all configured knowledge sources

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
