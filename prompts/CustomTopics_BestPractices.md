# Regular Topics Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio regular topic YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/topic-authoring-best-practices and https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/trigger-phrases-best-practices.

Check and improve:
1. Trigger phrases optimization (5-10 varied, natural phrases under 10 words)
2. Topic structure and organization (bite-size, reusable)
3. Conversational design and user experience
4. Entity usage and slot filling optimization
5. Variable management and data flow
6. Integration with other topics and system components
7. Question design and response handling
8. YAML structure and formatting

Focus on official Microsoft recommendations for topic authoring, trigger phrases, conversational design, and user experience. Provide corrected YAML if issues found.
```

## Component-Specific Guidelines

### ✅ Regular Topics Checklist
- [ ] 5-10 optimized trigger phrases
- [ ] Clear topic purpose and scope
- [ ] Bite-size topic structure
- [ ] Conversational prompts and responses
- [ ] Proper entity usage and slot filling
- [ ] Effective variable management
- [ ] Good integration with other topics
- [ ] User-friendly question design
- [ ] Appropriate topic size and complexity
- [ ] YAML structure and formatting correct

### 🎯 Topic Structure & Organization

**Bite-Size Topics:**
- Single, clear purpose per topic
- Manageable topic complexity
- Reusable components and logic
- Clear separation of concerns
- Easy maintenance and updates

**Topic Relationships:**
- Proper redirect actions to other topics
- Input/output variable management
- Shared logic extraction to reusable topics
- Clear topic hierarchy and dependencies
- Integration with system topics

**Conversation Flow:**
- Logical question sequences
- Natural conversation progression
- Appropriate branching and conditions
- User choice handling and validation
- Graceful error handling and recovery

### 💬 Conversational Design

**Question Design:**
- Clear and specific prompts
- User-friendly language and tone
- Appropriate question types and entities
- Helpful context and instructions
- Progress indication for multi-step flows

**Response Handling:**
- Comprehensive entity value coverage
- User input validation and error handling
- Contextual and personalized responses
- Follow-up questions and clarifications
- Integration with subsequent topic flow

**User Experience:**
- Natural conversation flow
- Appropriate use of quick replies and suggestions
- Clear progress indicators
- Help and clarification options
- Consistent tone and personality

### 🏷️ Entity Usage & Slot Filling

**Entity Selection:**
- Appropriate entity types for data collection
- Comprehensive value lists and synonyms
- User-friendly display names
- Proper entity scope and reusability
- Integration with conversation flow

**Slot Filling Optimization:**
- Efficient entity extraction from user input
- Skip unnecessary questions when entities detected
- Clear entity validation and error handling
- Appropriate default values and suggestions
- Integration with topic logic

### 🔗 Integration & Reusability

**Topic Integration:**
- Proper redirect actions to other topics
- Variable passing and data sharing
- Integration with system topics (Fallback, Error, etc.)
- External service and action integration
- Knowledge source and search integration

**Reusability Design:**
- Shared logic extraction to separate topics
- Common entity definitions and reuse
- Template patterns for similar topics
- Modular design for easy maintenance
- Configuration-driven topic behavior

### 📊 Performance & Monitoring

**Topic Performance:**
- Trigger phrase effectiveness monitoring
- User completion rate tracking
- Error rate and failure point analysis
- Response time and efficiency optimization
- User satisfaction measurement

**Continuous Improvement:**
- Analytics-driven trigger phrase refinement
- User feedback integration
- A/B testing for conversation flows
- Regular review and optimization cycles
- Knowledge base updates and improvements

### 🔧 Technical Implementation

**Variable Management:**
- Proper variable scoping and naming
- Data type validation and handling
- Variable cleanup and memory management
- Cross-topic variable sharing
- Integration with external data sources

**Error Handling:**
- Input validation and error prevention
- Clear error messages and recovery options
- Fallback behavior for unexpected inputs
- Integration with system error handling
- User guidance and assistance

### 📚 Reference Guidelines
- [Topic Authoring Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/topic-authoring-best-practices)
- [Trigger Phrases Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/trigger-phrases-best-practices)
- [Conversational Design](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/choose-effective-trigger-phrases)
- [Entity and Slot Filling](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/slot-filling-best-practices)
