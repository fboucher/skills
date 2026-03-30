---
name: text-editor
description: Critic and improve technical documentation, blog posts, and articles for clarity, structure, and publication readiness. Use when reviewing text content or when user asks to edit, critique, review, or improve written documentation.
---

# Text Editor Skill

## Overview

This skill provides comprehensive text criticism for technical writing. It evaluates:
- **Clarity**: Sentence structure, word choice, jargon
- **Structure**: Organization, flow, logical progression
- **Repetition**: Repeated words, phrases, or ideas
- **Typography**: Flags long dashes (--) usage
- **Visual aids**: Suggests code snippets, diagrams, or tables where needed
- **Publication readiness**: Identifies weaknesses that block publication

## Workflow

### 1. Initial Read & Assessment

Read the entire document to understand:
- Purpose and audience
- Technical level assumed
- Current structure and organization

### 2. Systematic Analysis

Analyze and report on each dimension:

#### Clarity Check
- Complex or ambiguous sentences
- Undefined jargon or acronyms
- Passive voice overuse
- Wordy phrases that could be concise
- Missing context or assumptions

#### Structure Analysis
- Logical flow between sections
- Paragraph coherence
- Introduction adequacy
- Conclusion strength
- Section ordering

#### Repetition Detection
- Repeated words within 3-sentence window
- Repeated phrases or ideas
- Redundant explanations
- Same concept stated differently multiple times

#### Typography Flags
- Long dashes (`--`) — flag ALL instances
- Inconsistent punctuation
- Incorrect spacing after punctuation

#### Visual Aid Suggestions
For each technical concept, evaluate if a:
- **Code snippet** would clarify implementation
- **Diagram** would show relationships/flow
- **Table** would compare options/parameters
- **List** would break down steps/components

Mark suggestions with: `[VISUAL: code|diagram|table|list]`

#### Publication Weak Points
Flag issues that block publication:
- Missing sections or incomplete explanations
- Unsupported claims
- Inconsistent terminology
- Grammar/style issues
- Audience mismatch
- Missing prerequisites

### 3. Output Format

Present criticism in structured format:

```
## Clarity Issues
- [Line X] Description of issue and suggested fix

## Structure Issues
- [Section Y] Description and suggestion

## Repetition
- [Line X] "repeated phrase" - suggest alternatives

## Typography Flags
- [Line X] "--" found - consider em dash (—) or rewording

## Visual Aid Suggestions
- [Line X] Concept: [VISUAL: code|diagram|table|list]
  Why: explanation

## Publication Blockers
- [Priority] Issue description
```

### 4. Actionable Recommendations

End with prioritized list of changes needed before publication:
1. **Critical**: Must fix
2. **Important**: Should fix
3. **Nice-to-have**: Consider fixing

## Tips

- Be specific with line numbers and sections
- Provide concrete suggestions, not just criticism
- Consider the target audience's expertise level
- Balance thoroughness with actionable feedback
