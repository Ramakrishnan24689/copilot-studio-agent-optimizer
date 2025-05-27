# Regular Topics Best Practices Prompt

## GitHub Copilot Chat Prompt

```
Review this Microsoft Copilot Studio regular topic YAML against official best practices from https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/topic-authoring-best-practices and https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/trigger-phrases-best-practices.

⚠️ CRITICAL YAML FORMATTING: 
- PRESERVE the exact indentation and formatting when providing corrected YAML
- YAML is indentation-sensitive and incorrect spacing will break the file structure
- Use exactly 2 spaces for each indentation level consistently
- NEVER use tabs - only spaces
- Maintain proper alignment for all nested elements
- DO NOT modify structural elements like `id:`, `kind:`, `beginDialog:`, `intent:` - these are framework-required
- DO NOT change line breaks or combine separate YAML properties on the same line

🚨 STRUCTURAL PRESERVATION:
- Keep `id: main` and `intent:` on separate lines exactly as they are
- Preserve all framework-required YAML structure (kind, beginDialog, actions, etc.)
- Only modify content within triggerQueries, prompts, and activity messages
- Never merge separate YAML properties onto the same line

🎯 MINIMAL CHANGES ONLY: Only suggest changes that:
- Fix clear violations of Microsoft's official best practices
- Address significant security, performance, or functionality issues  
- Have substantial impact on user experience or bot effectiveness
- Are explicitly recommended in official Microsoft documentation

🚫 AVOID:
- Adding unnecessary complexity (Switch statements, multiple questions, nested logic)
- Creative additions that weren't in the original topic
- Expanding simple topics into complex multi-step flows
- Adding features not explicitly requested or needed
- Over-engineering basic functionality
- Modifying YAML structure elements (id, kind, beginDialog, intent, actions)
- Changing indentation of existing properly formatted YAML
- Combining separate YAML properties on the same line

✅ FOCUS ON:
1. **TRIGGER PHRASES OPTIMIZATION** (5-10 varied, natural phrases under 10 words):
   - Use conversational, natural language
   - Vary sentence structure and length
   - Include different ways users might ask the same thing
   - Avoid overly technical or verbose phrases
   - Test for overlap with other topics
   - Keep phrases under 10 words for better recognition
   
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

### 📚 Reference Guidelines
- [Topic Authoring Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/topic-authoring-best-practices)
- [Trigger Phrases Best Practices](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/trigger-phrases-best-practices)
- [Choosing Effective Trigger Phrases](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/choose-effective-trigger-phrases)
- [Topic Triggering Guidelines](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/triggering-topics)
