# Triggers & Intent Recognition Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio trigger configuration YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/trigger-phrases-best-practices and https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/triggering-topics.

Check and improve:
1. Trigger phrase optimization (5-10 varied, natural phrases under 10 words)
2. Intent definition clarity and specificity
3. Topic overlap prevention and disambiguation
4. Natural language understanding effectiveness
5. Priority settings and behavior configuration
6. Include/exclude settings for intent selection
7. YAML structure and trigger configuration

Focus on official Microsoft recommendations for trigger phrase creation, NLU optimization, and topic triggering effectiveness. Provide corrected YAML if issues found.
```

## Component-Specific Guidelines

### ✅ Triggers & Intent Recognition Checklist
- [ ] 5-10 trigger phrases per topic (optimal range)
- [ ] Varied sentence structures and key terms
- [ ] Complete phrases (avoid single words)
- [ ] Under 10 words per phrase
- [ ] Natural, conversational language
- [ ] Unique verb/noun combinations
- [ ] No generic or ambiguous terms
- [ ] No obvious overlap with other topics
- [ ] Proper intent display name and configuration
- [ ] Appropriate include/exclude settings for intent selection

### 🎯 Trigger Phrase Optimization

**Quality Guidelines:**
- Use complete, natural phrases users would actually say
- Vary sentence structure and vocabulary
- Avoid single-word triggers (increases confusion)
- Keep phrases under 10 words for clarity
- Include unique verb and noun combinations
- Remove generic terms like "help", "info", "details"

**Overlap Prevention:**
- Compare trigger phrases across topics
- Avoid using same words in different topics
- Create disambiguation topics for similar intents
- Use entity extraction to reduce similar topics
- Monitor "Multiple Topics Matched" occurrences

**Natural Language Understanding:**
- Balance number of trigger phrases between topics
- Use real user data when possible
- Test with varied phrasings and synonyms
- Consider different ways users express intent
- Account for conversational context

### 🔍 Intent Configuration

**Intent Settings:**
- Clear and descriptive display names
- Appropriate includeInOnSelectIntent settings
- Proper priority and behavior configuration
- Integration with topic flow and conversation

**Triggering Behavior:**
- OnRecognizedIntent for standard topics
- OnSelectIntent for disambiguation scenarios
- Priority settings for topic competition
- Interruption policies and behavior

### 📊 Monitoring & Optimization

**Performance Indicators:**
- Topic triggering accuracy
- Multiple topics matched frequency
- Fallback topic activation rates
- User satisfaction and conversation success

**Continuous Improvement:**
- Analyze unrecognized utterances in fallback
- Add trigger phrases based on user interactions
- Refine existing phrases for better recognition
- Balance trigger phrase distribution across topics

### 📚 Reference Guidelines
- [Trigger Phrases Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/trigger-phrases-best-practices)
- [Topic Triggering](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/triggering-topics)
- [Natural Language Understanding](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-ai-features)
