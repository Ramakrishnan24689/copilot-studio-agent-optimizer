# Entities & Data Types Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio entity YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/slot-filling-best-practices and entity configuration guidelines.

Check and improve:
1. Entity type selection and configuration (ClosedList, Regex, ML, etc.)
2. Item definitions with clear display names and synonyms
3. Smart matching enablement and optimization
4. Entity reusability and naming conventions
5. Comprehensive value coverage for use cases
6. User-friendly display names and descriptions
7. Integration with topic slot filling
8. YAML structure and entity metadata

Focus on official Microsoft recommendations for entity design, slot filling optimization, and natural language understanding effectiveness. Provide corrected YAML if issues found.
```

## Component-Specific Guidelines

### ✅ Entities & Data Types Checklist
- [ ] Appropriate entity type selected (ClosedList, Regex, ML, etc.)
- [ ] Comprehensive value coverage for use case
- [ ] Clear, user-friendly display names
- [ ] Synonyms and variations included where appropriate
- [ ] Smart matching enabled when beneficial
- [ ] Consistent naming conventions followed
- [ ] Entity scope and reusability considered
- [ ] YAML structure and formatting correct
- [ ] Integration with topics optimized

### 🎯 Key Configuration Areas

**Entity Type Selection:**
- ClosedList for predefined, finite options
- Regex for pattern-based validation (emails, phones, etc.)
- ML entities for flexible, learning-based recognition
- Number entities for numeric values with ranges
- DateTime entities for temporal data
- Geography entities for location-based data

**Value Definition:**
- Comprehensive coverage of expected user inputs
- Logical grouping and organization
- Consistent value formatting and structure
- Appropriate granularity level
- Future expansion considerations

**Smart Matching Configuration:**
- Enable for better user input recognition
- Consider performance implications
- Test with various input formats
- Balance accuracy with processing speed
- Monitor and adjust based on usage patterns

### 🏷️ Entity Design Best Practices

**Display Names:**
- Clear, descriptive, and user-friendly
- Consistent capitalization and formatting
- Avoid technical jargon or internal codes
- Consider internationalization requirements
- Maintain brevity while being descriptive

**Value Organization:**
- Logical grouping of related items
- Hierarchical structure when appropriate
- Consistent ordering (alphabetical, by importance, etc.)
- Avoid duplicates and overlapping values
- Consider user mental models and expectations

**Synonyms and Variations:**
- Include common alternative phrasings
- Account for plural and singular forms
- Consider abbreviations and acronyms
- Include colloquial and informal terms
- Test with real user input patterns

### 🔄 Slot Filling Optimization

**Entity Integration:**
- Seamless integration with topic question nodes
- Efficient slot filling without redundant questions
- Clear validation and error handling
- Appropriate default values and suggestions
- Progressive disclosure for complex entities

**User Experience:**
- Natural conversation flow
- Clear prompts when entity clarification needed
- Helpful examples and guidance
- Error recovery mechanisms
- Confirmation patterns for critical values

**Performance Considerations:**
- Optimize entity size for processing speed
- Balance comprehensiveness with performance
- Consider caching for frequently used entities
- Monitor recognition accuracy and speed
- Regular review and optimization cycles

### 📊 Entity Types and Use Cases

**ClosedList Entities:**
- Predefined options (sizes, colors, categories)
- Multiple choice selections
- Status values and states
- Product types and variations
- Service offerings and packages

**Regex Entities:**
- Email addresses and contact information
- Phone numbers and postal codes
- Product SKUs and identification numbers
- Custom format validation
- Pattern-based data extraction

**ML Entities:**
- Names and free-text identification
- Flexible categorization needs
- Context-sensitive recognition
- Learning from user interactions
- Adaptive recognition patterns

### 🔧 Technical Implementation

**YAML Structure:**
- Proper indentation and formatting
- Consistent property naming
- Clear item organization
- Appropriate use of IDs and references
- Maintainable structure for updates

**Integration Points:**
- Topic question node compatibility
- Variable assignment and processing
- Condition and branching logic integration
- External system data mapping
- API and service integration preparation

**Maintenance Considerations:**
- Version control for entity changes
- Testing procedures for entity updates
- Impact analysis for modification
- Documentation and change tracking
- Rollback procedures if needed

### 🌐 Scalability and Reusability

**Entity Reuse:**
- Design for cross-topic utilization
- Avoid topic-specific entity definitions
- Consider global vs. local entity scope
- Plan for entity library development
- Standardize common entity patterns

**Future Expansion:**
- Anticipate new values and categories
- Design flexible entity structures
- Plan for internationalization needs
- Consider API-driven entity updates
- Implement dynamic entity loading where appropriate

### 📈 Performance Monitoring

**Recognition Accuracy:**
- Monitor entity recognition success rates
- Track user correction patterns
- Analyze failed recognition attempts
- Implement feedback loops for improvement
- Regular accuracy assessment cycles

**Usage Analytics:**
- Track most/least used entity values
- Identify missing values from user inputs
- Monitor entity performance impact
- Analyze slot filling efficiency
- User satisfaction with entity interactions

### 📚 Reference Guidelines
- [Entity Types](https://learn.microsoft.com/en-us/microsoft-copilot-studio/entities)
- [Slot Filling Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/slot-filling-best-practices)
- [Natural Language Understanding](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-ai-features)
