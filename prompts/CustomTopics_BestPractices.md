# Regular Topics Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio regular topic YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/topic-authoring-best-practices and https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/trigger-phrases-best-practices.

**KEY MICROSOFT BEST PRACTICES TO APPLY:**

**📝 TRIGGER PHRASE GUIDELINES** *(Source: [Trigger Phrases Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/trigger-phrases-best-practices))*:
- **5-10 phrases per topic**: Provide sufficient variety without overwhelming the NLU model
- **Under 10 words per phrase**: Keep them concise and focused - "When are you open" not "Can you please tell me when your store hours are"
- **Natural language**: Use words and phrases real users would actually say, based on production data when possible
- **Vary sentence structure**: Mix question types and key terms - "When are you closed", "Daily open hours", "Store hours"
- **Unique verbs and nouns**: Each topic should have distinct language patterns to avoid overlap
- **Complete phrases**: Avoid single words like "Store" - use "Find my nearest store" instead
- **Avoid entity variations**: Don't list all entity examples - the NLU automatically considers variations

**🎯 TOPIC ORGANIZATION** *(Source: [Topic Authoring Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/topic-authoring-best-practices))*:
- **Create bite-size topics**: Break down large topics into manageable, reusable components
- **Single responsibility**: Each topic should handle one clear task or question type
- **Avoid topic overlap**: Monitor and resolve ambiguous trigger phrases that could match multiple topics
- **Use disambiguation**: Create catch-all topics with slot filling for unclear user intent
- **Leverage entities**: Use one "Order" topic with "FoodType" entity instead of separate "Order Pizza", "Order Burger" topics

**💬 CONVERSATION DESIGN**:
- **Clear prompts**: Ask specific questions that guide users effectively
- **Helpful responses**: Provide value and next steps, not just confirmations
- **User-friendly language**: Match the tone and complexity to your audience
- **Example**: Change "Which energy drink would you like to order?" → "What energy drink would you like to know more about? Here are our available options:"

**⚡ OPTIMIZATION GUIDELINES**:
- **Balance trigger phrases**: Keep similar numbers across topics to avoid NLU bias
- **Test with real data**: Use actual user utterances when creating trigger phrases
- **Monitor "Multiple Topics Matched"**: High occurrence indicates overlap issues that need resolution
- **Consider conversation context**: NLU behaves differently at conversation start vs. during topic switching

⚠️ CRITICAL YAML FORMATTING: 
- PRESERVE the exact indentation and formatting when providing corrected YAML
- YAML is indentation-sensitive and incorrect spacing will break the file structure
- Use exactly 2 spaces for each indentation level consistently
- NEVER use tabs - only spaces
- Maintain proper alignment for all nested elements
- DO NOT modify structural elements like `id:`, `kind:`, `beginDialog:`, `intent:` - these are framework-required
- DO NOT change line breaks or combine separate YAML properties on the same line

🔧 EDITING PRECISION REQUIREMENTS:
- When using replace_string_in_file, include ONLY the content that needs changing
- Include 3-5 lines of context before and after to ensure precise matching
- NEVER include framework elements (id:, kind:, actions:) in replacement strings
- Make separate, targeted edits rather than large block replacements
- After each edit, verify that no structural elements were accidentally modified
- If YAML structure gets corrupted, restore from original before continuing

🚨 STRUCTURAL PRESERVATION:
- Keep `id: main` and `intent:` on separate lines exactly as they are
- Preserve all framework-required YAML structure (kind, beginDialog, actions, etc.)
- Only modify content within triggerQueries, prompts, and activity messages
- Never merge separate YAML properties onto the same line

🔒 **WHEN NOT TO MAKE CHANGES - READ THIS FIRST:**

**If the topic configuration already meets Microsoft best practices, DO NOT modify anything. Simply respond with:**
"✅ **No changes needed.** This topic configuration already follows Microsoft Copilot Studio best practices with proper trigger phrases, conversation flow, and correct YAML formatting."

**Only make changes if you identify CLEAR violations of official Microsoft best practices.**

🎯 MINIMAL CHANGES ONLY: Only suggest changes that:
- Fix clear violations of Microsoft's official best practices
- Address significant security, performance, or functionality issues  
- Have substantial impact on user experience or bot effectiveness
- Are explicitly recommended in official Microsoft documentation

🚫 AVOID:
- Making changes when configuration is already well-structured
- Adding unnecessary complexity (Switch statements, multiple questions, nested logic)
- Creative additions that weren't in the original topic
- Expanding simple topics into complex multi-step flows
- Adding features not explicitly requested or needed
- Over-engineering basic functionality
- Modifying YAML structure elements (id, kind, beginDialog, intent, actions)
- Changing indentation of existing properly formatted YAML
- Combining separate YAML properties on the same line
- Making stylistic changes that don't improve functionality

## 🔍 EVALUATION FRAMEWORK - Use This Decision Tree

**STEP 1: Quick Assessment**
- ✅ Does it have 5-10 varied, natural trigger phrases under 10 words?
- ✅ Are conversation flows clear and user-friendly?
- ✅ Is the YAML properly formatted?
- ✅ Are responses helpful and guide users effectively?

**If ALL answers are YES → No changes needed!**

**STEP 2: Only if Step 1 reveals issues, check for:**
- Too few (<5) or too many (>10) trigger phrases
- Trigger phrases over 10 words or unnatural language
- YAML formatting errors
- Unclear or unhelpful conversation flow
- Topic overlap issues

**STEP 3: Response Format**
- **No Issues Found**: "✅ No changes needed. Configuration follows best practices."
- **Issues Found**: Make minimal targeted fixes only for identified violations

✅ FOCUS ON:
1. **TRIGGER PHRASES OPTIMIZATION** (5-10 varied, natural phrases under 10 words):
   - Use conversational, natural language
   - Vary sentence structure and length
   - Include different ways users might ask the same thing
   - Avoid overly technical or verbose phrases
   - Test for overlap with other topics
   - Keep phrases under 10 words for better recognition

**📝 SAFE EDITING PRACTICES:**
When modifying YAML files:
1. **Target content only** - Edit trigger queries, prompts, and activity messages
2. **Use precise boundaries** - Include context lines but avoid framework elements
3. **Make incremental changes** - Edit one section at a time, not large blocks
4. **Verify after each edit** - Check that structure remains intact
5. **Example of SAFE edit boundary:**
   ```yaml
   triggerQueries:
     - old phrase 1    ← Include this context
     - phrase to change ← Target this content
     - old phrase 3    ← Include this context
   ```
6. **Example of UNSAFE edit boundary:**
   ```yaml
   intent:              ← NEVER include framework elements
     triggerQueries:    ← NEVER include structural elements
       - phrase to change
   ```
   
2. Simple prompt and response improvements
3. Basic variable naming and entity usage fixes
4. Critical YAML syntax errors
5. Essential user experience improvements

⚠️ YAML STRUCTURE WARNING: NEVER modify these framework elements:
- `id: main` (keep exactly as is, on separate line)
- `kind:` properties 
- `beginDialog:` structure
- `intent:` (must be on separate line after id)
- `actions:` structure
- Do NOT combine properties like "id: main intent:" - this breaks YAML

KEEP IT SIMPLE: Most topics should remain simple question-answer patterns unless they already have complex logic that needs fixing.
```

## Component-Specific Guidelines

### ✅ Regular Topics Checklist
- [ ] **TRIGGER PHRASES**: 5-10 optimized phrases (short, natural, varied)
  - [ ] Each phrase under 10 words
  - [ ] Natural, conversational language
  - [ ] Varied sentence structures
  - [ ] No overlap with other topics
  - [ ] Cover different ways users might ask
- [ ] Clear topic purpose and scope (single responsibility)
- [ ] Simple, maintainable structure (avoid over-engineering)
- [ ] User-friendly prompts and responses
- [ ] Proper entity usage (only when needed)
- [ ] Clean variable management
- [ ] Appropriate topic complexity (keep it simple)
- [ ] Correct YAML indentation (exactly 2 spaces per level)

### 🎯 Essential Fixes Only

**Trigger Phrase Optimization (PRIMARY FOCUS):**
- Keep 5-10 natural phrases under 10 words each
- Ensure variety in phrasing and structure (questions, statements, commands)
- Remove redundant or overly verbose phrases
- Use conversational, user-friendly language
- Test for overlap with other topics in the bot
- Include different user intents (information seeking, action requests, etc.)
- Examples of GOOD triggers: "book a room", "check availability", "what rooms do you have"
- Examples of BAD triggers: "I would like to make a reservation for a room", "room booking functionality"
- Use conversational, user-friendly language

**Basic Structure Improvements:**
- Maintain single, clear purpose per topic
- Keep complexity manageable and maintainable
- Fix critical YAML syntax errors
- Ensure proper variable scoping

**Simple User Experience:**
- Clear, concise prompts and questions
- Appropriate entity usage (don't over-engineer)
- Basic error handling where essential
- Natural conversation flow

**YAML Technical Requirements:**
- Exactly 2 spaces for each indentation level
- Never use tabs - only spaces
- Maintain consistent alignment for nested elements
- Preserve original structure when making improvements
- DO NOT modify framework properties: `id:`, `kind:`, `beginDialog:`, `intent:`, `actions:`
- DO NOT combine YAML properties on the same line (e.g., "id: main intent:" is INVALID)
- Only edit content within arrays like triggerQueries and text content like prompts/activities

**🛡️ YAML VALIDATION CHECKLIST:**
After making any edits, verify these elements remain intact:
- [ ] `id: main` appears alone on its line with proper indentation
- [ ] `intent:` appears alone on its line directly after id
- [ ] All `kind:` properties are preserved and properly indented
- [ ] `triggerQueries:` array items start with `- ` and proper indentation
- [ ] Entity `items:` array maintains consistent indentation
- [ ] No YAML properties are combined on the same line
- [ ] All closing braces `{}` are properly positioned

**🚨 COMMON YAML ERRORS TO AVOID:**
- Combining properties: `id: main intent:` ❌
- Missing line breaks: `displayName: Value - id: Next` ❌
- Inconsistent indentation in arrays ❌
- Missing spaces after colons: `id:main` ❌
- Tab characters instead of spaces ❌

### 📚 Reference Guidelines
- [Topic Authoring Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/topic-authoring-best-practices)
- [Trigger Phrases Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/trigger-phrases-best-practices)
- [Choosing Effective Trigger Phrases](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/choose-effective-trigger-phrases)
- [Topic Triggering Guidelines](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/triggering-topics)
