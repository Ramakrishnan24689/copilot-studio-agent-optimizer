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

🔒 **WHEN NOT TO MAKE CHANGES - READ THIS FIRST:**

**If the entity configuration already meets Microsoft best practices, DO NOT modify anything. Simply respond with:**
"✅ **No changes needed.** This entity configuration already follows Microsoft Copilot Studio best practices with proper entity type, item definitions, and correct YAML formatting."

**Only make changes if you identify CLEAR violations of official Microsoft best practices.**

🎯 MINIMAL CHANGES ONLY: Only suggest changes that:
- Fix clear violations of Microsoft's official best practices
- Address significant security, performance, or functionality issues
- Have substantial impact on user experience or bot effectiveness
- Are explicitly recommended in official Microsoft documentation

🚫 AVOID:
- Making changes when configuration is already well-structured
- Adding unnecessary complexity to entity configurations
- Creative additions that weren't in the original entity
- Over-engineering basic entity functionality
- Adding advanced features unless explicitly needed
- Modifying entity YAML structure elements (kind, definition, items, displayName)
- Changing indentation of existing properly formatted YAML
- Combining separate YAML properties on the same line
- Making stylistic changes that don't improve functionality

## 🔍 EVALUATION FRAMEWORK - Use This Decision Tree

**STEP 1: Quick Assessment**
- ✅ Is the entity type appropriate (ClosedList, Regex, ML)?
- ✅ Are item definitions clear and comprehensive?
- ✅ Is the YAML properly formatted?
- ✅ Are display names and synonyms well-defined?

**If ALL answers are YES → No changes needed!**

**STEP 2: Only if Step 1 reveals issues, check for:**
- Inappropriate entity type selection
- Missing or unclear item definitions
- YAML formatting errors
- Poor display names or synonym coverage

**STEP 3: Response Format**
- **No Issues Found**: "✅ No changes needed. Configuration follows best practices."
- **Issues Found**: Make minimal targeted fixes only for identified violations

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

## 🔧 EDITING PRECISION REQUIREMENTS

**CRITICAL**: When editing entity YAML files, tools must use surgical precision:

- ✅ **Target content only**: Modify item values, display names, synonyms, patterns
- ❌ **Never touch framework**: Avoid `kind:`, `definition:`, `items:`, `displayName:`
- ✅ **Preserve entity types**: Keep ClosedList, Regex, ML entity structures intact
- ❌ **No structural changes**: Never merge separate YAML entity properties

## 📝 SAFE EDITING PRACTICES

### ✅ SAFE: Entity Content Updates
```yaml
# BEFORE:
displayName: "Drink"
items:
  - name: "cola"

# AFTER: 
displayName: "Energy Drink Types"
items:
  - name: "cola"
    synonyms: ["coke", "pepsi"]
```

### ❌ DANGEROUS: Framework Modification
```yaml
# NEVER DO THIS:
kind: ClosedListEntity definition: {...}  # ← BREAKS YAML STRUCTURE

# CORRECT:
kind: ClosedListEntity
definition:
  items: [...]
```

## 🛡️ ENTITY YAML VALIDATION CHECKLIST

After every edit, verify:
- [ ] All entity properties remain on separate lines
- [ ] Entity type (ClosedList, Regex, ML) structure preserved
- [ ] Item definitions and synonyms properly formatted
- [ ] No framework elements (`kind:`, `definition:`, `items:`, `displayName:`) modified
- [ ] Smart matching and recognition settings intact

## 🚨 ENTITY-SPECIFIC YAML ERRORS TO AVOID

1. **Property Merging**: `kind: ClosedListEntity definition:` ← NEVER
2. **Type Breaking**: Modifying entity type structure ← RECOGNITION FAILURE
3. **Item Corruption**: Invalid item or synonym format ← MATCHING ERROR
4. **Definition Violation**: Wrong definition schema for entity type ← PARSING FAILURE
```

## Component-Specific Guidelines

### 🎯 SLOT FILLING FUNDAMENTALS *(Source: [Microsoft Learn - Slot Filling Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/slot-filling-best-practices))*

**What is Slot Filling:**
- Automatically extracts required information from user queries to skip unnecessary questions
- Example: "I'd like to order 3 large blue t-shirts" → Topic (Order), Quantity (3), Color (Blue), Item Type (T-Shirt)
- Reduces conversation friction by intelligently gathering information
- Skips questions where information is already provided in triggering query

**Entity Value Storage:**
- All extracted values stored in variables for reuse throughout conversation
- Variables maintain data regardless of how values were entered
- Enables sophisticated conversation flows with persistent data

### 📝 ENTITY TYPE SELECTION *(Source: [Microsoft Learn - Slot Filling Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/slot-filling-best-practices))*

**Built-in Entities:**
- Use for common cases: Email, Date/time, Person name, Phone number, Color, Country, City, Number, Money
- Handle multiple variations automatically (e.g., "$100", "a hundred dollars", "100 dollars" → Money: 100)
- Powerful natural language understanding without configuration

**Custom Entity Types:**
- **Closed List**: Predefined list of values with synonyms support
- **Regular Expression (RegEx)**: Pattern-based matching for consistent formats (e.g., INC000001 for ticket numbers)
- **ML Entities**: Machine learning-based extraction for complex patterns

### 🔧 CLOSED LIST ENTITY OPTIMIZATION *(Source: [Microsoft Learn - Slot Filling Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/slot-filling-best-practices))*

**Synonym Best Practices:**
- Add relevant synonyms to expand matching logic (e.g., "hiking" → "trekking", "mountaineering")
- Synonyms improve topic triggering by increasing trigger phrase weight
- Include negative words as synonyms for complaint-type entities
- One example trigger phrase with entity enables NLU generalization to all variations

**Smart Matching Configuration:**
- Enable Smart Matching for fuzzy logic interpretation
- Automatically corrects misspellings in user input
- Semantic expansion (e.g., "softball" matches "baseball")
- Reduces exact match requirements while maintaining accuracy

### 🎨 REGULAR EXPRESSION CREATIVITY *(Source: [Microsoft Learn - Slot Filling Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/slot-filling-best-practices))*

**Pattern-Based Entity Design:**
- Use RegEx to avoid entity confusion when multiple same-type entities exist
- Example for "bring 2 towels and 1 pillow to room 101":
  - Towel Quantity: `[1-9] towel`
  - Pillow Quantity: `[1-9] pillow`  
  - Room Number: `[0-9]{3}`
- Context-specific patterns prevent extraction ambiguity

### 🗃️ LARGE DATASET ALTERNATIVES *(Source: [Microsoft Learn - Slot Filling Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/slot-filling-best-practices))*

**External Data Sources:**
- For large/evolving datasets (products, customers), use external services instead of closed lists
- Pass user utterance to external service via Power Automate cloud flow
- Validate accuracy or ask user confirmation before proceeding

**Dataverse Integration:**
- Built-in Dataverse Search supports fuzzy matching with confidence scores
- Returns best results even with full sentence queries
- Ideal for dynamic, searchable reference data

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
