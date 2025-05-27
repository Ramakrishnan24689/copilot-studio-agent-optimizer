# Conversation Management Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio conversation management topic YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-system-topics and conversation flow guidelines.

Check and improve:
1. User confirmation flows and validation
2. Conversation state management and variable handling
3. Variable cleanup and reset procedures
4. User experience and messaging quality
5. Integration with other system topics
6. Error handling and recovery options
7. Conversation outcome tracking
8. YAML structure and flow logic

Focus on official Microsoft recommendations for conversation control, state management, and user experience design. Provide corrected YAML if issues found.
```

## Component-Specific Guidelines

### ✅ Conversation Management Checklist
- [ ] Clear user confirmation flows implemented
- [ ] Proper conversation state management
- [ ] Variable cleanup procedures defined
- [ ] User-friendly prompts and messaging
- [ ] Seamless integration with system topics
- [ ] Error handling and recovery paths
- [ ] Conversation outcome tracking
- [ ] Appropriate start behavior configuration
- [ ] Clear dialog management and control flow

### 🎯 Key Management Areas

**State Management:**
- Conversation variable scope and lifecycle
- Proper variable initialization and cleanup
- State persistence across dialog transitions
- Memory management and performance
- Context preservation during topic switches

**User Confirmation Flows:**
- Clear confirmation prompts and options
- Binary choice handling (Yes/No, Continue/Stop)
- User intent validation and clarification
- Graceful handling of unclear responses
- Retry mechanisms for invalid inputs

**Dialog Control:**
- StartBehavior configuration (CancelOtherTopics, etc.)
- Dialog replacement and redirection
- Topic queue management
- Interruption handling and policies
- Conversation flow orchestration

### 🔄 Reset & Restart Operations

**Conversation Reset:**
- Complete variable cleanup (ConversationScopedVariables)
- Dialog cancellation and queue clearing
- User state reinitialization
- Context restoration for fresh start
- Integration with greeting and start topics

**Start Over Functionality:**
- User confirmation before restart
- Partial vs. complete conversation reset
- State preservation for important data
- Seamless transition to initial state
- User communication during reset process

### 🎯 User Experience Design

**Confirmation Patterns:**
- Clear and specific confirmation prompts
- Easy-to-understand choices and options
- Consistent confirmation flow across topics
- User-friendly language and tone
- Appropriate default selections

**Error Recovery:**
- Graceful handling of invalid responses
- Clear error messages and guidance
- Recovery options and alternative paths
- User assistance and help availability
- Escalation paths for persistent issues

### 📊 Conversation Outcomes

**Outcome Tracking:**
- Conversation satisfaction measurement
- Success and failure outcome capture
- User journey completion tracking
- Integration with analytics and reporting
- Continuous improvement data collection

**Integration Points:**
- Connection with End of Conversation topic
- Integration with escalation workflows
- Handoff to human agents when needed
- Data collection for conversation improvement
- Feedback loop implementation

### 🔧 Technical Implementation

**Variable Management:**
- Proper variable scoping (Topic, Global, Conversation)
- Variable naming conventions and consistency
- Data type handling and validation
- Memory efficiency and cleanup
- Cross-topic variable sharing

**Flow Control:**
- Conditional logic and branching
- Loop prevention and infinite recursion protection
- Topic priority and precedence rules
- Interruption handling and recovery
- Performance optimization for complex flows

### 📚 Reference Guidelines
- [System Topics](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-system-topics)
- [Variable Management](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-variables)
- [Conversation Design](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/topic-authoring-best-practices)
