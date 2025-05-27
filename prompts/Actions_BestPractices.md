# Actions & Power Automate Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio action YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-use-flow and action integration guidelines.

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

🎯 MINIMAL CHANGES ONLY: Only suggest changes that:
- Fix clear violations of Microsoft's official best practices
- Address significant security, performance, or functionality issues
- Have substantial impact on user experience or bot effectiveness
- Are explicitly recommended in official Microsoft documentation

🚫 AVOID:
- Adding unnecessary complexity to action configurations
- Creative additions that weren't in the original action
- Over-engineering basic action functionality
- Adding advanced features unless explicitly needed
- Modifying action YAML structure elements (kind, name, connectionReferenceName)
- Changing indentation of existing properly formatted YAML
- Combining separate YAML properties on the same line

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
