# Knowledge & Search Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio knowledge/search component YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/nlu-boost-conversations and knowledge integration guidelines.

⚠️ CRITICAL YAML FORMATTING: 
- PRESERVE the exact indentation and formatting when providing corrected YAML
- YAML is indentation-sensitive and incorrect spacing will break the file structure
- Use exactly 2 spaces for each indentation level consistently
- NEVER use tabs - only spaces
- Maintain proper alignment for all nested elements
- DO NOT modify structural elements like `kind:`, `name:`, `knowledgeSourceId:` - these are framework-required
- DO NOT change line breaks or combine separate YAML properties on the same line

🚨 STRUCTURAL PRESERVATION FOR KNOWLEDGE:
- Keep knowledge framework properties (`kind:`, `name:`, `knowledgeSourceId:`, `contentLocation:`) exactly as they are
- Preserve all knowledge configuration structure (SearchAndSummarizeContent, file references)
- Only modify content within descriptions and search parameters
- Never merge separate YAML properties onto the same line

🎯 MINIMAL CHANGES ONLY: Only suggest changes that:
- Fix clear violations of Microsoft's official best practices
- Address significant security, performance, or functionality issues
- Have substantial impact on user experience or bot effectiveness
- Are explicitly recommended in official Microsoft documentation

🚫 AVOID:
- Adding unnecessary complexity to search configurations
- Creative additions that weren't in the original knowledge setup
- Over-engineering basic search functionality
- Adding advanced features unless explicitly needed
- Modifying knowledge YAML structure elements (kind, name, knowledgeSourceId, contentLocation)
- Changing indentation of existing properly formatted YAML
- Combining separate YAML properties on the same line

✅ FOCUS ON:
1. SearchAndSummarizeContent configuration fixes
2. Basic knowledge source corrections
3. Essential variable handling improvements
4. Critical YAML syntax errors

⚠️ KNOWLEDGE YAML STRUCTURE WARNING: NEVER modify these framework elements:
- `kind:` properties (keep exactly as is)
- `name:` (must be on separate line)
- `knowledgeSourceId:` structure
- `contentLocation:` properties
- Do NOT combine properties like "kind: name:" - this breaks YAML
5. Basic performance setting corrections

KEEP IT SIMPLE: Most knowledge configurations should maintain their core functionality unless there are clear violations to fix.
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

## ⚠️ YAML Formatting Critical
- Use exactly 2 spaces for each indentation level
- Never use tabs - only spaces
- Maintain consistent alignment for all nested elements
- Preserve original indentation structure when making improvements

### 📚 Reference Guidelines
- [Knowledge Integration](https://learn.microsoft.com/en-us/microsoft-copilot-studio/nlu-boost-conversations)
- [Generative AI Features](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-ai-features)
- [Search and Summarize Content](https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-search-summarize)
