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

🔒 **WHEN NOT TO MAKE CHANGES - READ THIS FIRST:**

**If the knowledge configuration already meets Microsoft best practices, DO NOT modify anything. Simply respond with:**
"✅ **No changes needed.** This knowledge configuration already follows Microsoft Copilot Studio best practices with proper knowledge sources, search configuration, and correct YAML formatting."

**Only make changes if you identify CLEAR violations of official Microsoft best practices.**

🎯 MINIMAL CHANGES ONLY: Only suggest changes that:
- Fix clear violations of Microsoft's official best practices
- Address significant security, performance, or functionality issues
- Have substantial impact on user experience or bot effectiveness
- Are explicitly recommended in official Microsoft documentation

🚫 AVOID:
- Making changes when configuration is already well-structured
- Adding unnecessary complexity to search configurations
- Creative additions that weren't in the original knowledge setup
- Over-engineering basic search functionality
- Adding advanced features unless explicitly needed
- Modifying knowledge YAML structure elements (kind, name, knowledgeSourceId, contentLocation)
- Changing indentation of existing properly formatted YAML
- Combining separate YAML properties on the same line
- Making stylistic changes that don't improve functionality

## 🔍 EVALUATION FRAMEWORK - Use This Decision Tree

**STEP 1: Quick Assessment**
- ✅ Is SearchAndSummarizeContent setup correctly?
- ✅ Is the YAML properly formatted?

**If ALL answers are YES → No changes needed!**

**STEP 2: Only if Step 1 reveals issues, check for:**
- Inaccessible or misconfigured knowledge sources
- Poor search configuration or content handling
- YAML formatting errors
- Inappropriate content permissions or locations

**STEP 3: Response Format**
- **No Issues Found**: "✅ No changes needed. Configuration follows best practices."
- **Issues Found**: Make minimal targeted fixes only for identified violations

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

## 🔧 EDITING PRECISION REQUIREMENTS

**CRITICAL**: When editing knowledge/search YAML files, tools must use surgical precision:

- ✅ **Target content only**: Modify descriptions, search parameters, response settings
- ❌ **Never touch framework**: Avoid `kind:`, `name:`, `knowledgeSourceId:`, `contentLocation:`
- ✅ **Preserve sources**: Keep knowledge source references intact
- ❌ **No structural changes**: Never merge separate YAML knowledge properties

## 📝 SAFE EDITING PRACTICES

### ✅ SAFE: Search Parameter Updates
```yaml
# BEFORE:
description: "Search content"

# AFTER: 
description: "Search and summarize relevant content from knowledge base"
```

### ❌ DANGEROUS: Framework Modification
```yaml
# NEVER DO THIS:
kind: SearchAndSummarizeContent name: KnowledgeSearch  # ← BREAKS YAML

# CORRECT:
kind: SearchAndSummarizeContent
name: KnowledgeSearch
```

## 🛡️ KNOWLEDGE YAML VALIDATION CHECKLIST

After every edit, verify:
- [ ] All knowledge properties remain on separate lines
- [ ] Knowledge source IDs and content locations preserved
- [ ] Search configuration parameters properly formatted
- [ ] No framework elements (`kind:`, `name:`, `knowledgeSourceId:`, `contentLocation:`) modified
- [ ] Variable handling for search results intact

## 🚨 KNOWLEDGE-SPECIFIC YAML ERRORS TO AVOID

1. **Property Merging**: `kind: SearchAndSummarizeContent name:` ← NEVER
2. **Source Breaking**: Modifying knowledgeSourceId format ← SEARCH FAILURE
3. **Location Corruption**: Invalid contentLocation references ← ACCESS ERROR
4. **Parameter Mismatch**: Wrong search parameter types ← QUERY FAILURE
```

## Component-Specific Guidelines

### 📚 KNOWLEDGE SOURCES FUNDAMENTALS *(Source: [Microsoft Learn - Knowledge Sources Overview](https://learn.microsoft.com/en-us/microsoft-copilot-studio/nlu-boost-conversations))*

**Supported Knowledge Source Types:**
- **Public Website**: External Bing search on provided websites (unlimited in generative mode, 4 URLs in classic)
- **Documents**: Dataverse-uploaded files with document content search (unlimited in generative mode)
- **SharePoint**: GraphSearch integration with user authentication (unlimited in generative mode, 4 URLs in classic)
- **Dataverse**: Retrieval-augmented generative technique with user authentication (unlimited in generative mode, 2 sources in classic)
- **Enterprise Data**: Copilot connectors with Microsoft Search indexing (unlimited in generative mode, 2 per agent in classic)

**Authentication Requirements:**
- SharePoint, Dataverse, and Enterprise data require Microsoft Entra ID authentication
- Agent user authentication ensures content access matches user permissions
- Configure user authentication before adding authenticated knowledge sources

### 🔍 SEARCH & SUMMARIZE CONFIGURATION *(Source: [Microsoft Learn - Knowledge Sources Overview](https://learn.microsoft.com/en-us/microsoft-copilot-studio/nlu-boost-conversations))*

**Generative Answers Integration:**
- Conversational boosting system topic automatically includes all agent-level knowledge sources
- Knowledge sources act as primary information or fallback when authored topics can't answer
- Enables quick deployment of functional agents without extensive topic authoring

**Knowledge Source Descriptions:**
- Write clear, descriptive knowledge source descriptions for generative orchestration
- Descriptions help GPT filter and select appropriate knowledge sources
- Use specific terminology that matches expected user queries

### 🎛️ ORCHESTRATION MODES *(Source: [Microsoft Learn - Knowledge Sources Overview](https://learn.microsoft.com/en-us/microsoft-copilot-studio/nlu-boost-conversations))*

**Classic Orchestration:**
- Limited knowledge source numbers per type (see supported types above)
- Supports custom data sources and Bing Custom Search
- Can embed generative answers nodes in specific topics
- All specified knowledge sources are searched

**Generative Orchestration:**
- Unlimited uploaded files are always searched
- GPT selects top 4 knowledge sources based on descriptions
- Does not support custom data or Bing Custom Search
- More intelligent source selection but fewer total sources

### ⚙️ ADVANCED CONFIGURATION *(Source: [Microsoft Learn - Knowledge Sources Overview](https://learn.microsoft.com/en-us/microsoft-copilot-studio/nlu-boost-conversations))*

**Content Moderation:**
- Agent-level settings in Generative AI page
- Topic-level settings in generative answers nodes (takes precedence)
- Moderation levels: Lowest (more answers, less accuracy) to Highest (fewer answers, more relevant)
- Default level is High for balanced results

**Enhanced Search Results:**
- Requires Microsoft 365 Copilot license in same tenant
- Requires "Authenticate with Microsoft" setting
- Supports semantic search for improved results
- SharePoint/connectors support files up to 200 MB (512 MB for PDF/PPTX/DOCX)

**Web Search & General Knowledge:**
- Web Search provides real-time information beyond predefined knowledge
- General knowledge setting allows AI foundational knowledge usage
- Turn off general knowledge to ground agent only in specific knowledge sources

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
