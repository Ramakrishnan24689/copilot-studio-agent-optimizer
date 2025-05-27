# System Topics Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio system topic YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/fallback-topic and system topic guidelines. 

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

🎯 MINIMAL CHANGES ONLY: Only suggest changes that:
- Fix clear violations of Microsoft's official best practices
- Address significant security, performance, or functionality issues
- Have substantial impact on user experience or bot effectiveness
- Are explicitly recommended in official Microsoft documentation

🚫 AVOID:
- Adding unnecessary complexity or features
- Creative additions that weren't in the original topic
- Over-engineering basic system topic functionality
- Adding advanced logic unless explicitly needed
- Modifying system topic YAML structure elements (kind, beginDialog, intent, id)
- Changing indentation of existing properly formatted YAML
- Combining separate YAML properties on the same line

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

KEEP IT SIMPLE: Most system topics should maintain their core functionality unless there are clear violations to fix.
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
