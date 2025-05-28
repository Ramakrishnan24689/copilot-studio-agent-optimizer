# Bot Settings & Configuration Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio bot settings YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/configuration-fundamentals and bot configuration guidelines.

⚠️ CRITICAL YAML FORMATTING: 
- PRESERVE the exact indentation and formatting when providing corrected YAML
- YAML is indentation-sensitive and incorrect spacing will break the file structure
- Use exactly 2 spaces for each indentation level consistently
- NEVER use tabs - only spaces
- Maintain proper alignment for all nested elements
- DO NOT modify structural elements like `kind:`, `settings:`, `authentication:` - these are framework-required
- DO NOT change line breaks or combine separate YAML properties on the same line

🚨 STRUCTURAL PRESERVATION FOR BOT SETTINGS:
- Keep settings framework properties (`kind:`, `settings:`, `authentication:`, `aiFeatures:`) exactly as they are
- Preserve all bot configuration structure (language, security, features)
- Only modify content within setting values and configuration parameters
- Never merge separate YAML properties onto the same line

🔒 **WHEN NOT TO MAKE CHANGES - READ THIS FIRST:**

**If the bot settings configuration already meets Microsoft best practices, DO NOT modify anything. Simply respond with:**
"✅ **No changes needed.** This bot settings configuration already follows Microsoft Copilot Studio best practices with proper security, authentication, and feature settings."

**Only make changes if you identify CLEAR violations of official Microsoft best practices.**

🎯 MINIMAL CHANGES ONLY: Only suggest changes that:
- Fix clear violations of Microsoft's official best practices
- Address significant security, performance, or functionality issues
- Have substantial impact on user experience or bot effectiveness
- Are explicitly recommended in official Microsoft documentation

🚫 AVOID:
- Making changes when configuration is already well-structured
- Adding unnecessary complexity to bot settings
- Creative additions that weren't in the original configuration
- Over-engineering basic bot functionality
- Adding advanced features unless explicitly needed
- Modifying bot settings YAML structure elements (kind, settings, authentication, aiFeatures)
- Changing indentation of existing properly formatted YAML
- Combining separate YAML properties on the same line
- Making stylistic changes that don't improve functionality

## 🔍 EVALUATION FRAMEWORK - Use This Decision Tree

**STEP 1: Quick Assessment**
- ✅ Are security and authentication settings properly configured?
- ✅ Are AI features appropriately enabled for the bot's purpose?
- ✅ Is the YAML properly formatted?
- ✅ Are language and regional settings correct?

**If ALL answers are YES → No changes needed!**

**STEP 2: Only if Step 1 reveals issues, check for:**
- Insecure authentication configurations
- Inappropriate AI feature settings
- YAML formatting errors
- Missing critical bot configuration

**STEP 3: Response Format**
- **No Issues Found**: "✅ No changes needed. Configuration follows best practices."
- **Issues Found**: Make minimal targeted fixes only for identified violations

✅ FOCUS ON:
1. Authentication configuration fixes
2. Basic AI and GPT setting corrections
3. Essential feature enablement adjustments
4. Critical YAML syntax errors

⚠️ BOT SETTINGS YAML STRUCTURE WARNING: NEVER modify these framework elements:
- `kind:` properties (keep exactly as is)
- `settings:` (must be on separate line)
- `authentication:` structure
- `aiFeatures:` properties
- Do NOT combine properties like "kind: settings:" - this breaks YAML
5. Basic security setting corrections

## 🔧 EDITING PRECISION REQUIREMENTS

**CRITICAL**: When editing bot settings YAML files, tools must use surgical precision:

- ✅ **Target content only**: Modify setting values, feature toggles, configuration parameters
- ❌ **Never touch framework**: Avoid `kind:`, `settings:`, `authentication:`, `aiFeatures:`
- ✅ **Preserve security**: Keep authentication and security settings intact
- ❌ **No structural changes**: Never merge separate YAML configuration properties

## 📝 SAFE EDITING PRACTICES

### ✅ SAFE: Configuration Value Updates
```yaml
# BEFORE:
language: "en-us"

# AFTER: 
language: "en-us"
enableTypingIndicator: true
```

### ❌ DANGEROUS: Framework Modification
```yaml
# NEVER DO THIS:
kind: BotSettings settings: {...}  # ← BREAKS YAML STRUCTURE

# CORRECT:
kind: BotSettings
settings:
  language: "en-us"
```

## 🛡️ BOT SETTINGS YAML VALIDATION CHECKLIST

After every edit, verify:
- [ ] All configuration properties remain on separate lines
- [ ] Authentication settings preserved and secure
- [ ] AI feature toggles properly formatted
- [ ] No framework elements (`kind:`, `settings:`, `authentication:`, `aiFeatures:`) modified
- [ ] Language and localization settings intact

## 🚨 BOT SETTINGS-SPECIFIC YAML ERRORS TO AVOID

1. **Settings Merging**: `kind: BotSettings settings:` ← NEVER
2. **Auth Breaking**: Modifying authentication structure ← SECURITY FAILURE
3. **Feature Corruption**: Invalid AI feature configuration ← FEATURE FAILURE
4. **Type Mismatch**: Wrong data types for boolean/string settings ← PARSING ERROR
```

## Component-Specific Guidelines

### 🔐 AUTHENTICATION CONFIGURATION *(Source: [Microsoft Learn - Configuration Fundamentals](https://learn.microsoft.com/en-us/microsoft-copilot-studio/configuration-fundamentals))*

**Authentication Options:**
- **No Authentication**: Allows anyone with the link to interact with the agent. Use only for public, non-sensitive information. ⚠️ **Security Risk**: Consider authentication for organizational or sensitive use cases.
- **Authenticate with Microsoft**: Automatic Microsoft Entra ID authentication for Teams. Only Teams channel is available. Provides `User.ID` and `User.DisplayName` variables.
- **Authenticate Manually**: Supports multiple providers (Microsoft Entra ID V2, Generic OAuth2). Provides full authentication variables including `User.AccessToken` and `User.IsLoggedIn`.

**Security Best Practices:**
- Enable "Require users to sign in" for agents accessing sensitive information
- Use least privilege principle when setting OAuth scopes
- Apply authentication especially for organizational use cases
- Consider data loss prevention (DLP) policies that require authentication

### 🛡️ SECURITY & GOVERNANCE *(Source: [Microsoft Learn - Configuration Fundamentals](https://learn.microsoft.com/en-us/microsoft-copilot-studio/configuration-fundamentals))*

**Agent Sharing Controls:**
- **No Authentication**: Cannot control organizational access - anyone with link can chat
- **Authenticate with Microsoft**: Full organizational control via agent sharing (Teams only)
- **Authenticate Manually**: Organizational control available with Microsoft Entra ID providers

**Required Configuration:**
- Authentication changes only take effect after publishing
- Plan authentication changes carefully before implementation
- Validate authentication variables in topics before publishing
- Fix "Unknown variables" errors when changing authentication types

### 🌐 LANGUAGE & LOCALIZATION *(Source: [Microsoft Learn - Configuration Fundamentals](https://learn.microsoft.com/en-us/microsoft-copilot-studio/configuration-fundamentals))*

**Language Settings:**
- Set primary language appropriate for target audience
- Configure fallback language for unsupported locales
- Enable typing indicators for better user experience
- Consider regional date/time formats and cultural preferences

**Multi-language Support:**
- Plan for international deployments early
- Test authentication across different language settings
- Validate that authentication providers work in target locales

### ⚙️ AI FEATURES & CAPABILITIES

**Generative AI Settings:**
- Configure content moderation levels (Lowest to Highest)
- Enable/disable general knowledge access based on use case
- Set appropriate orchestration mode (Classic vs Generative)
- Configure enhanced search results for Microsoft 365 tenants

**Feature Toggles:**
- Enable only necessary AI features to reduce complexity
- Test feature combinations thoroughly before production
- Monitor performance impact of enabled features

### ✅ Bot Settings & Configuration Checklist
- [ ] Authentication mode appropriate for use case
- [ ] Access control policy properly configured
- [ ] AI settings optimized for bot functionality
- [ ] Essential features enabled (GenerativeActions, SemanticSearch)
- [ ] Recognizer type matches bot requirements
- [ ] Basic security settings configured
- [ ] Template version is current and supported
- [ ] Correct YAML structure and formatting

### 🎯 Essential Configuration Areas

**Authentication & Security:**
- Authentication mode selection (None, Integrated, Manual)
- Access control policy assignment
- Basic security considerations

**AI Settings:**
- GPT settings optimization for bot functionality
- Generative actions enablement when needed
- Semantic search configuration
- Recognizer type selection

**Feature Configuration:**
- Essential feature enablement
- Template version management
- Language and localization basics

### 📚 Reference Guidelines
- [Bot Configuration Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/configuration-fundamentals)
- [Security Settings](https://learn.microsoft.com/en-us/microsoft-copilot-studio/configuration-security)

**AI & GPT Settings:**
- useModelKnowledge optimization
- File analysis enablement
- Semantic search configuration
- Latest models opt-in consideration
- Generative AI recognizer setup
- Knowledge integration settings

**Feature Configuration:**
- GenerativeActionsEnabled for advanced AI features
- Knowledge source integration
- External service connections
- Performance optimization features
- Analytics and monitoring capabilities

## ⚠️ YAML Formatting Critical
- Use exactly 2 spaces for each indentation level
- Never use tabs - only spaces
- Maintain consistent alignment for all nested elements
- Preserve original indentation structure when making improvements

### 📚 Reference Guidelines
- [Bot Configuration Fundamentals](https://learn.microsoft.com/en-us/microsoft-copilot-studio/configuration-fundamentals)
- [Security Overview](https://learn.microsoft.com/en-us/microsoft-copilot-studio/security-overview)
- [AI Features Configuration](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-ai-features)
