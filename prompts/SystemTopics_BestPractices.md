# System Topics Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio system topic YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/fallback-topic and system topic guidelines.

**KEY MICROSOFT SYSTEM TOPIC BEST PRACTICES:**

**🏗️ SYSTEM TOPIC FUNDAMENTALS** *(Source: [System Topics Overview](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-system-topics))*:
- **Built-in functionality**: System topics are automatically added and handle essential agent behaviors
- **Cannot be deleted**: Only disable if not needed, but most are essential for proper agent function
- **Auto-triggering**: Respond to specific system events like errors, escalations, conversation start/end
- **Customizable content**: Can modify messages and flow while preserving trigger mechanisms

**🔄 CORE SYSTEM TOPICS BEHAVIOR**:
- **Conversation Start**: Greets users and introduces agent capabilities at conversation beginning
- **Fallback**: Handles unrecognized user input with helpful redirect options
- **Multiple Topics Matched**: Provides disambiguation when user input matches multiple topics
- **Escalate**: Manages handoff to human agents when "talk to agent" is detected
- **On Error**: Provides error information with codes, conversation ID, and timestamps for debugging
- **End of Conversation**: Confirms query resolution and provides closure

**💡 FALLBACK TOPIC OPTIMIZATION** *(Source: [Fallback Topic Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/fallback-topic))*:
- **Learn from failures**: Track unmatched phrases to improve existing trigger phrases or create new topics
- **Offload Q&A pairs**: Use external systems via Power Automate for large volumes of single-turn conversations
- **Agent personality**: Integrate "chitchat" responses for trivial questions to make agent more engaging
- **Generative AI integration**: Connect to Azure OpenAI Service for handling complex unmatched queries
- **Knowledge base integration**: Use Azure Cognitive Services Question Answering for FAQ handling

**⚠️ SYSTEM TOPIC BEST PRACTICES**:
- **Don't over-customize**: Maintain essential system behaviors while personalizing user-facing messages
- **Monitor "Multiple Topics Matched"**: High frequency indicates trigger phrase overlap that needs resolution
- **Proper error handling**: Ensure On Error topic provides helpful information without exposing technical details
- **Escalation clarity**: Make it clear when and how users can reach human support
- **Conversation flow**: Ensure smooth transitions between system topics and custom topics 

⚠️ CRITICAL YAML FORMATTING: 
- PRESERVE the exact indentation and formatting when providing corrected YAML
- YAML is indentation-sensitive and incorrect spacing will break the file structure
- Use exactly 2 spaces for each indentation level consistently
- NEVER use tabs - only spaces
- Maintain proper alignment for all nested elements
- DO NOT modify structural elements like `kind:`, `beginDialog:`, `intent:` - these are framework-required
- DO NOT change line breaks or combine separate YAML properties on the same line

🚨 STRUCTURAL PRESERVATION FOR SYSTEM TOPICS:
- Keep system topic framework properties (`kind:`, `beginDialog:`, `intent:`, `id:`) exactly as they are
- Preserve all system topic structure (OnUnknownIntent, OnConversationStart, OnError, etc.)
- Only modify content within messages, prompts, and condition values
- Never merge separate YAML properties onto the same line

🔒 **WHEN NOT TO MAKE CHANGES - READ THIS FIRST:**

**If the system topic configuration already meets Microsoft best practices, DO NOT modify anything. Simply respond with:**
"✅ **No changes needed.** This system topic configuration already follows Microsoft Copilot Studio best practices with proper trigger configuration, conversation flow, and correct YAML formatting."

**Only make changes if you identify CLEAR violations of official Microsoft best practices.**

🎯 MINIMAL CHANGES ONLY: Only suggest changes that:
- Fix clear violations of Microsoft's official best practices
- Address significant security, performance, or functionality issues
- Have substantial impact on user experience or bot effectiveness
- Are explicitly recommended in official Microsoft documentation

🚫 AVOID:
- Making changes when configuration is already well-structured
- Adding unnecessary complexity or features
- Creative additions that weren't in the original topic
- Over-engineering basic system topic functionality
- Adding advanced logic unless explicitly needed
- Modifying system topic YAML structure elements (kind, beginDialog, intent, id)
- Changing indentation of existing properly formatted YAML
- Combining separate YAML properties on the same line
- Making stylistic changes that don't improve functionality

## 🔍 EVALUATION FRAMEWORK - Use This Decision Tree

**STEP 1: Quick Assessment**
- ✅ Are system triggers properly configured for their purpose?
- ✅ Are conversation flows appropriate for system functionality?
- ✅ Is the YAML properly formatted?
- ✅ Are error handling and user messaging clear?

**If ALL answers are YES → No changes needed!**

**STEP 2: Only if Step 1 reveals issues, check for:**
- Incorrect system trigger configuration
- Poor error handling or user messaging
- YAML formatting errors
- Inappropriate conversation flow for system topics

**STEP 3: Response Format**
- **No Issues Found**: "✅ No changes needed. Configuration follows best practices."
- **Issues Found**: Make minimal targeted fixes only for identified violations

✅ FOCUS ON:
1. System trigger configuration fixes (OnUnknownIntent, OnConversationStart, etc.)
2. Basic conversation flow improvements
3. Essential error handling corrections
4. Critical YAML syntax errors

⚠️ SYSTEM TOPIC YAML STRUCTURE WARNING: NEVER modify these framework elements:
- `id: main` (keep exactly as is, on separate line)
- `kind:` properties 
- `beginDialog:` structure
- `intent:` (must be on separate line after id)
- Do NOT combine properties like "id: main intent:" - this breaks YAML
5. User messaging clarity improvements

## 🔧 EDITING PRECISION REQUIREMENTS

**CRITICAL**: When editing YAML files, tools must use surgical precision to avoid structural corruption:

- ✅ **Target content only**: Modify trigger phrases, messages, prompts, condition values
- ❌ **Never touch framework**: Avoid `kind:`, `beginDialog:`, `intent:`, `id:`, `actions:`
- ✅ **Preserve boundaries**: Keep exact indentation and line breaks
- ❌ **No line merging**: Never combine separate YAML properties on the same line

## 📝 SAFE EDITING PRACTICES

### ✅ SAFE: Content-Only Changes
```yaml
# BEFORE:
prompt: "Which energy drink would you like to order?"

# AFTER: 
prompt: "What energy drink would you like to know more about?"
```

### ❌ DANGEROUS: Framework Modification
```yaml
# NEVER DO THIS:
id: main intent: OnRecognizedIntent  # ← BREAKS YAML STRUCTURE

# CORRECT:
id: main
intent: OnRecognizedIntent
```

## 🛡️ YAML VALIDATION CHECKLIST

After every edit, verify:
- [ ] All YAML properties remain on separate lines
- [ ] Indentation follows 2-space standard consistently  
- [ ] No framework elements (`kind:`, `beginDialog:`, `intent:`, `id:`) were modified
- [ ] Structural hierarchy preserved (parent-child relationships intact)
- [ ] No syntax errors (colons, quotes, brackets properly closed)

## 🚨 COMMON YAML ERRORS TO AVOID

1. **Line Merging**: `id: main intent: OnRecognizedIntent` ← NEVER
2. **Indentation Mix**: Tabs + spaces ← BREAKS PARSING
3. **Property Deletion**: Removing required framework properties ← FATAL
4. **Quote Mismatches**: `prompt: "Hello world'` ← SYNTAX ERROR
5. **Bracket Imbalance**: Missing closing `]` or `}` ← PARSING FAILURE
```

## Component-Specific Guidelines

### ✅ System Topic Checklist
- [ ] **SYSTEM TRIGGERS**: Proper system trigger type configured
  - [ ] OnUnknownIntent (Fallback)
  - [ ] OnConversationStart 
  - [ ] OnRecognizedIntent with optimized trigger phrases (Greeting, Goodbye)
  - [ ] OnError for error handling topics
- [ ] Clear conversation outcomes defined
- [ ] Appropriate priority settings
- [ ] User-friendly messaging and tone
- [ ] Proper variable initialization and cleanup
- [ ] Error handling and recovery paths
- [ ] Integration points with other topics
- [ ] YAML structure and formatting

### 🎯 Focus Areas by System Topic Type

**Fallback Topic:**
- OnUnknownIntent trigger properly configured
- Escalation after multiple failed attempts (typically 3)
- Learning opportunities from unrecognized utterances
- Integration with knowledge search or external systems
- Graceful degradation and user guidance

**Conversation Start:**
- OnConversationStart trigger implementation
- Welcoming and informative initial message
- Conversation state initialization
- User expectation setting
- Brand personality expression

**Greeting Topic:**
- **TRIGGER PHRASES**: OnRecognizedIntent with appropriate trigger phrases
  - Include: "hello", "hi", "good morning", "hey there", "greetings"
  - Keep phrases natural and varied (5-7 common greetings)
  - Avoid overly formal or lengthy phrases
- Friendly and professional tone
- Context-aware responses
- Conversation flow initialization
- Integration with conversation start

**Goodbye Topic:**
- **TRIGGER PHRASES**: OnRecognizedIntent with appropriate trigger phrases  
  - Include: "goodbye", "bye", "see you", "thanks bye", "exit"
  - Keep phrases natural and conversational (5-7 common farewells)
  - Cover different levels of formality
- Proper conversation ending confirmation
- User satisfaction checking
- Graceful conversation termination
- Data cleanup and session management
- Integration with End of Conversation system topic

### 🔧 Technical Implementation

**YAML Indentation Requirements:**
- Use exactly 2 spaces for each indentation level
- Never use tabs - only spaces
- Maintain consistent alignment for all nested elements
- Preserve original indentation structure when making improvements
- Test YAML syntax after any modifications

**System Topic Configuration:**
- Proper trigger configuration and conditions
- Variable management and state handling
- Integration with other system topics
- Error handling and recovery mechanisms
- Performance and flow optimization

### 📚 Reference Guidelines
- [Fallback Topic Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/fallback-topic)
- [System Topics Overview](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-system-topics)
- [Trigger Phrases Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/trigger-phrases-best-practices)
- [Topic Triggering Guidelines](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/triggering-topics)
- [Conversation Design Principles](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/topic-authoring-best-practices)
