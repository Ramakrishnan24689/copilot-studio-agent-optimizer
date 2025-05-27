# Knowledge & Search Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio knowledge/search component YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/nlu-boost-conversations and knowledge integration guidelines.

Check and improve:
1. SearchAndSummarizeContent configuration and implementation
2. Knowledge source integration and priority settings
3. Response quality and summarization effectiveness
4. Fallback handling for failed searches
5. Variable handling and data flow
6. Performance optimization (timeouts, caching)
7. Integration with conversation flow and other topics
8. YAML structure and formatting

Focus on official Microsoft recommendations for knowledge integration, generative AI features, and search optimization. Provide corrected YAML if issues found.
```

## Component-Specific Guidelines

### ✅ Knowledge & Search Checklist
- [ ] SearchAndSummarizeContent properly configured
- [ ] Knowledge sources correctly integrated
- [ ] Response variable handling optimized
- [ ] Search failure handling implemented
- [ ] Performance considerations addressed
- [ ] User experience during search operations
- [ ] Integration with topic priority system
- [ ] Semantic search optimization enabled

### 🎯 Key Configuration Areas

**SearchAndSummarizeContent Action:**
- Proper variable assignment for search results
- User input mapping and processing
- Response formatting and presentation
- Error handling for search failures
- Performance optimization settings

**Knowledge Source Integration:**
- Multiple knowledge source prioritization
- External data source connections
- File analysis and document processing
- Semantic search capabilities
- Content summarization quality

**Conversation Flow Integration:**
- Priority settings for knowledge topics
- Fallback behavior configuration
- Integration with main conversation topics
- User experience during knowledge retrieval

### 🔧 Performance Optimization
- Search timeout configurations
- Response caching strategies
- Knowledge source prioritization
- Content indexing optimization
- User experience during processing

### 📚 Reference Guidelines
- [Knowledge Integration](https://learn.microsoft.com/en-us/microsoft-copilot-studio/nlu-boost-conversations)
- [Generative AI Features](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-ai-features)
- [Search and Summarize Content](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-search-summarize)
