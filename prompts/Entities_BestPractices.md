# Entities & Data Types Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio entity YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/slot-filling-best-practices and entity configuration guidelines.

⚠️ CRITICAL YAML FORMATTING: 
- PRESERVE the exact indentation and formatting when providing corrected YAML
- YAML is indentation-sensitive and incorrect spacing will break the file structure
- Use exactly 2 spaces for each indentation level consistently
- NEVER use tabs - only spaces
- Maintain proper alignment for all nested elements
- DO NOT modify structural elements like `kind:`, `definition:`, `items:` - these are framework-required
- DO NOT change line breaks or combine separate YAML properties on the same line

🚨 STRUCTURAL PRESERVATION FOR ENTITIES:
- Keep entity framework properties (`kind:`, `definition:`, `items:`, `displayName:`) exactly as they are
- Preserve all entity configuration structure (ClosedListEntity, RegexEntity, etc.)
- Only modify content within item values, display names, and synonyms
- Never merge separate YAML properties onto the same line

🎯 MINIMAL CHANGES ONLY: Only suggest changes that:
- Fix clear violations of Microsoft's official best practices
- Address significant security, performance, or functionality issues
- Have substantial impact on user experience or bot effectiveness
- Are explicitly recommended in official Microsoft documentation

🚫 AVOID:
- Adding unnecessary complexity to entity configurations
- Creative additions that weren't in the original entity
- Over-engineering basic entity functionality
- Adding advanced features unless explicitly needed
- Modifying entity YAML structure elements (kind, definition, items, displayName)
- Changing indentation of existing properly formatted YAML
- Combining separate YAML properties on the same line

✅ FOCUS ON:
1. Entity type selection corrections (ClosedList, Regex, ML, etc.)
2. Basic item definition improvements
3. Essential display name and synonym fixes
4. Critical YAML syntax errors

⚠️ ENTITY YAML STRUCTURE WARNING: NEVER modify these framework elements:
- `kind:` properties (keep exactly as is)
- `definition:` (must be on separate line)
- `items:` structure
- `displayName:` properties
- Do NOT combine properties like "kind: definition:" - this breaks YAML
5. Basic smart matching setting corrections

KEEP IT SIMPLE: Most entities should maintain their core functionality unless there are clear violations to fix.
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

## ⚠️ YAML Formatting Critical
- Use exactly 2 spaces for each indentation level
- Never use tabs - only spaces
- Maintain consistent alignment for all nested elements
- Preserve original indentation structure when making improvements

### 📚 Reference Guidelines
- [Entity Types](https://learn.microsoft.com/en-us/microsoft-copilot-studio/entities)
- [Slot Filling Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/slot-filling-best-practices)
- [Natural Language Understanding](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-ai-features)
