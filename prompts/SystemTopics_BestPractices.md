# System Topics Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio system topic YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/fallback-topic and system topic guidelines. 

Check and improve:
1. System trigger configuration (OnUnknownIntent, OnConversationStart, etc.)
2. Conversation flow logic and conditions
3. User experience and messaging quality
4. Error handling and escalation patterns
5. Variable management and scope
6. Integration with other system topics
7. YAML formatting and structure

Focus on official Microsoft recommendations for system topic behavior, user communication, and conversation management. Provide corrected YAML if issues found.
```

## Component-Specific Guidelines

### ✅ System Topic Checklist
- [ ] Proper system trigger type (OnUnknownIntent, OnConversationStart, etc.)
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
- OnRecognizedIntent with appropriate trigger phrases
- Friendly and professional tone
- Context-aware responses
- Conversation flow initialization
- Integration with conversation start

**Goodbye Topic:**
- Proper conversation ending confirmation
- User satisfaction checking
- Graceful conversation termination
- Data cleanup and session management
- Integration with End of Conversation system topic

### 📚 Reference Guidelines
- [Fallback Topic Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/fallback-topic)
- [System Topics Overview](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-system-topics)
- [Conversation Design Principles](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/topic-authoring-best-practices)
