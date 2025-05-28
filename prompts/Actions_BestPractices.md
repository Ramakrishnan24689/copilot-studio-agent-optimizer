# Actions & Power Automate Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio action YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-use-flow and action integration guidelines.

**KEY MICROSOFT ACTIONS & POWER AUTOMATE BEST PRACTICES:**

**🔗 ACTION INTEGRATION FUNDAMENTALS** *(Source: [Power Automate Integration](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-use-flow))*:
- **Clear descriptions**: Provide meaningful, clear descriptions that help the agent orchestrator understand when to use the action
- **Proper input/output mapping**: Map flow inputs to topic variables and select relevant output parameters to return to the agent
- **Variable naming**: Use meaningful variable names like "City" instead of "Var1" for better maintainability
- **Flow validation**: Always test flows and use the flow checker to identify issues before deployment

**⚙️ ACTION CONFIGURATION**:
- **Description quality**: Write descriptions like "Get today's weather forecast at a provided city name or zip code" not just "Weather flow"
- **Input validation**: Ensure proper data types (String, Number, Boolean) match between topic variables and flow inputs
- **Output selection**: Only return necessary output parameters to avoid overwhelming the conversation
- **Error handling**: Include proper error responses when actions fail or timeout

**🧪 TESTING & TROUBLESHOOTING** *(Source: [Power Automate Integration](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-use-flow))*:
- **Test thoroughly**: Always test actions in the Test agent panel with real data
- **Flow checker**: Use flow designer tab to identify configuration issues
- **Topic checker**: Verify action nodes are properly configured in topics
- **Refresh actions**: Reload flows after Power Automate changes using the Refresh option

**🔄 ACTION LIFECYCLE MANAGEMENT**:
- **Change flows**: Use Change flow icon when hovering over action nodes to modify or replace flows
- **Version control**: Refresh action nodes after updating flows in Power Automate
- **Dependencies**: Consider impact on topics when modifying or deleting flows
- **Reusability**: Design flows to be reusable across multiple topics when possible

**🛡️ SECURITY & PERFORMANCE**:
- **Connection security**: Ensure proper authentication and connection management
- **Data validation**: Validate inputs before passing to external systems
- **Timeout handling**: Set appropriate timeouts for external service calls
- **Error boundaries**: Implement graceful degradation when actions fail

⚠️ CRITICAL YAML FORMATTING: 
- PRESERVE the exact indentation and formatting when providing corrected YAML
- YAML is indentation-sensitive and incorrect spacing will break the file structure
- Use exactly 2 spaces for each indentation level consistently
- NEVER use tabs - only spaces
- Maintain proper alignment for all nested elements
- DO NOT modify structural elements like `kind:`, `name:`, `connectionReferenceName:` - these are framework-required
- DO NOT change line breaks or combine separate YAML properties on the same line

🚨 STRUCTURAL PRESERVATION FOR ACTIONS:
- Keep action framework properties (`kind:`, `name:`, `connectionReferenceName:`) exactly as they are
- Preserve all action configuration structure (inputs, outputs, settings)
- Only modify content within parameter values and descriptions
- Never merge separate YAML properties onto the same line

🔒 **WHEN NOT TO MAKE CHANGES - READ THIS FIRST:**

**If the action configuration already meets Microsoft best practices, DO NOT modify anything. Simply respond with:**
"✅ **No changes needed.** This action configuration already follows Microsoft Copilot Studio best practices with proper connection references, clear descriptions, and correct YAML formatting."

**Only make changes if you identify CLEAR violations of official Microsoft best practices.**

🎯 MINIMAL CHANGES ONLY: Only suggest changes that:
- Fix clear violations of Microsoft's official best practices
- Address significant security, performance, or functionality issues
- Have substantial impact on user experience or bot effectiveness
- Are explicitly recommended in official Microsoft documentation

🚫 AVOID:
- Making changes when configuration is already well-structured
- Adding unnecessary complexity to action configurations
- Creative additions that weren't in the original action
- Over-engineering basic action functionality
- Adding advanced features unless explicitly needed
- Modifying action YAML structure elements (kind, name, connectionReferenceName)
- Changing indentation of existing properly formatted YAML
- Combining separate YAML properties on the same line
- Making stylistic changes that don't improve functionality

✅ FOCUS ON:
1. Connection reference configuration fixes
2. Basic input/output variable corrections
3. Essential error handling improvements
4. Critical YAML syntax errors

⚠️ ACTION YAML STRUCTURE WARNING: NEVER modify these framework elements:
- `kind:` properties (keep exactly as is)
- `name:` (must be on separate line)
- `connectionReferenceName:` structure
- Do NOT combine properties like "kind: name:" - this breaks YAML
5. Security setting corrections

## 🔧 EDITING PRECISION REQUIREMENTS

**CRITICAL**: When editing action YAML files, tools must use surgical precision:

- ✅ **Target content only**: Modify parameter values, descriptions, input/output settings
- ❌ **Never touch framework**: Avoid `kind:`, `name:`, `connectionReferenceName:`
- ✅ **Preserve connections**: Keep Power Automate integration intact
- ❌ **No structural changes**: Never merge separate YAML action properties

## 📝 SAFE EDITING PRACTICES

### ✅ SAFE: Parameter Value Updates
```yaml
# BEFORE:
description: "Get data"

# AFTER: 
description: "Retrieve customer feedback data from SharePoint"
```

### ❌ DANGEROUS: Framework Modification
```yaml
# NEVER DO THIS:
kind: AdaptiveAction name: GetData  # ← BREAKS YAML STRUCTURE

# CORRECT:
kind: AdaptiveAction
name: GetData
```

## 🛡️ ACTION YAML VALIDATION CHECKLIST

After every edit, verify:
- [ ] All action properties remain on separate lines
- [ ] Connection references still valid and properly formatted
- [ ] Input/output parameter mapping preserved
- [ ] No framework elements (`kind:`, `name:`, `connectionReferenceName:`) modified
- [ ] Security and authentication settings intact

## 🚨 ACTION-SPECIFIC YAML ERRORS TO AVOID

1. **Property Merging**: `kind: AdaptiveAction name:` ← NEVER
2. **Connection Breaking**: Modifying connectionReferenceName format ← INTEGRATION FAILURE
3. **Parameter Corruption**: Invalid input/output mappings ← RUNTIME ERROR
4. **Schema Violation**: Changing action type structure ← PARSING FAILURE

## 🔍 EVALUATION FRAMEWORK - Use This Decision Tree

**STEP 1: Quick Assessment**
- ✅ Does it have clear, descriptive action description?
- ✅ Are connection references properly configured?
- ✅ Is the YAML properly formatted?
- ✅ Are input/output mappings clear and validated?

**If ALL answers are YES → No changes needed!**

**STEP 2: Only if Step 1 reveals issues, check for:**
- Vague or missing action descriptions
- Connection reference errors
- YAML formatting errors
- Poor input/output variable mapping
- Missing error handling

**STEP 3: Response Format**
- **No Issues Found**: "✅ No changes needed. Configuration follows best practices."
- **Issues Found**: Make minimal targeted fixes only for identified violations

KEEP IT SIMPLE: Most actions should maintain their core functionality unless there are clear violations to fix.
```

## Component-Specific Guidelines

### ✅ Actions & Power Automate Checklist
- [ ] Connection reference properly configured
- [ ] Authentication mode and security settings appropriate
- [ ] Input variable mapping clear and validated
- [ ] Output variable handling optimized
- [ ] Error handling robust and user-friendly
- [ ] User communication during execution
- [ ] Performance timeouts configured
- [ ] Integration with conversation flow seamless

### 🎯 Key Configuration Areas

**Connection Configuration:**
- Connection reference setup and naming
- Authentication mode selection (Invoker vs Service)
- Security and access control considerations
- Connection sharing and reusability

**Variable Mapping:**
- Input parameter validation and formatting
- Output variable assignment and processing
- Data type handling and conversion
- Variable scope management

**Error Handling:**
- Connection failure scenarios
- Action execution errors
- Timeout handling
- User-friendly error messaging
- Recovery and retry mechanisms

**User Experience:**
- Loading messages during execution
- Progress indicators for long-running actions
- Clear success and failure communication
- Seamless integration with conversation flow

## ⚠️ YAML Formatting Critical
- Use exactly 2 spaces for each indentation level
- Never use tabs - only spaces
- Maintain consistent alignment for all nested elements
- Preserve original indentation structure when making improvements

### 📚 Reference Guidelines
- [Power Automate Integration](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-use-flow)
- [Connection Management](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-use-flow#use-flows-in-your-copilot)
- [Security Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/security-overview)
