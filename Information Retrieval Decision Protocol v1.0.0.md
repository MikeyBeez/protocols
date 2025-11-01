# Information Retrieval Decision Protocol v1.0.0
*Created: August 19, 2025*  
*Type: Foundation Protocol (Tier 2)*  
*Purpose: Systematic decision-making for when to use web search vs existing knowledge vs internal tools*

## Overview
This protocol provides a systematic decision tree for choosing the optimal information source: existing knowledge, internal tools (Brain, architecture docs, project files), or web search. Prevents both under-searching (missing current info) and over-searching (wasting time on known information).

## Triggers
- Any user question or request for information
- Encountering unknown terms or entities
- Need to verify or supplement provided information
- Complex queries requiring multiple information sources
- Uncertainty about information currency or accuracy

## Core Principle
**Check internal sources first, leverage existing knowledge, search for gaps and currency.**

## Decision Tree

### 🚫 **NEVER Search First**
Go directly to existing knowledge when:
- **Fundamental concepts**: Definitions, established theories, basic explanations
- **Slow-changing information**: Technical concepts, historical facts, stable processes
- **Programming/technical knowledge**: Well-established practices, syntax, common patterns
- **Mathematical/scientific principles**: Formulas, laws, established methodologies
- **Architecture/project questions**: When internal docs likely have answers

**Examples**:
- "How do for loops work in Python?"
- "What is the capital of France?"
- "Explain the Pythagorean theorem"
- "How does our Brain system work?" (check internal docs first)

### 🔍 **Search Immediately**
Skip other sources when:
- **Current events**: News, recent developments, breaking stories
- **Temporal indicators**: "Latest", "current", "recent", "2025", "today"
- **Rapidly changing data**: Prices, rates, status updates, trends
- **Unknown entities**: Terms, companies, people I don't recognize
- **Technical currency**: "Best practices for X in 2025", current framework versions
- **Real-time verification**: User asks to "check" or "verify" current information

**Examples**:
- "What's the latest news about AI regulation?"
- "Current price of Bitcoin"
- "Who won yesterday's election?"
- "Best practices for Next.js in 2025"
- "What is Anthropic's latest model?" (if beyond knowledge cutoff)

### 🤔 **Search After Initial Attempt**
Try knowledge first, then search if:
- **Incomplete confidence**: Information seems partial or uncertain
- **User requests verification**: "Can you verify this?" or "Is this still accurate?"
- **Complex synthesis needed**: Multiple current sources would strengthen answer
- **Knowledge gap identified**: Realize during response that current info would help
- **Conflicting information**: Need to resolve discrepancies with current sources

**Examples**:
- Provide known information, then: "Let me search for the latest updates..."
- "Based on my knowledge X is true, but let me verify current status..."

## Tool Priority Hierarchy

### 1. **Internal Tools First** (for relevant domains)
```
brain:brain_recall "topic"                    # Check Brain knowledge
mcp-architecture:arch_find_document "query"   # Architecture docs
project-finder:find_project "name"           # Project-specific info
filesystem-enhanced:search_files             # Local documentation
```

**When to use**: Project questions, documented processes, architecture queries, system-specific information

### 2. **Existing Knowledge** (for established information)
Answer directly when confident about:
- Stable, well-established information
- Topics within expertise and knowledge cutoff
- Fundamental concepts and explanations
- Technical knowledge unlikely to have changed

### 3. **Web Search** (for current/unknown information)
```
web_search "query"           # Current information search
web_fetch "specific_url"     # Deep dive into specific sources
```

**When to use**: Current events, unknown entities, rapidly changing information, verification requests

### 4. **Combined Approach** (for comprehensive answers)
- Start with internal tools for context
- Supplement with existing knowledge
- Search for current updates or verification
- Synthesize all sources for complete answer

## Implementation Guidelines

### Search Query Optimization
- **Keep queries concise**: 1-6 words for best results
- **Start broad, then narrow**: Begin with general terms, add specifics if needed
- **Include temporal markers**: "2025", "latest", "current" when currency matters
- **Never repeat similar queries**: Make each search unique

### Information Source Credibility
- **Favor original sources**: Company blogs, official docs, peer-reviewed papers
- **Avoid aggregators**: Unless specifically relevant to query
- **Prioritize recent sources**: 1-3 months for evolving topics
- **Note conflicting sources**: Acknowledge when sources disagree

### Response Construction
- **Lead with relevant info**: Start with most current/relevant information
- **Cite appropriately**: Use minimal quotes (<15 words) with proper attribution
- **Maintain objectivity**: Present balanced view when sources conflict
- **Be politically neutral**: Especially when referencing web content

## Quality Checks

### Before Searching
- [ ] Could internal tools have this information?
- [ ] Is this established knowledge I can answer confidently?
- [ ] Does the query require current/real-time information?
- [ ] Am I searching to avoid thinking vs. genuine need for current info?

### During Search
- [ ] Are search queries focused and unique?
- [ ] Am I checking original sources vs. aggregators?
- [ ] Am I noting source dates and credibility?
- [ ] Am I avoiding copyright violations in citations?

### After Search
- [ ] Did the search add value beyond existing knowledge?
- [ ] Are sources properly cited and minimal quotes used?
- [ ] Is the information synthesis balanced and objective?
- [ ] Would this approach work for similar future queries?

## Anti-Patterns to Avoid

❌ **Searching for well-known information**: Don't search for basic concepts  
❌ **Reflexive searching**: Searching without thinking if knowledge exists  
❌ **Redundant queries**: Repeating similar searches with slight variations  
❌ **Excessive citation**: Using >15 word quotes or multiple long quotes  
❌ **Ignoring internal tools**: Missing project-specific documented knowledge  

## Edge Cases

### Ambiguous Currency
When uncertain if information changes frequently:
- Provide known information first
- Offer to search for updates
- Example: "Based on my knowledge X, but I can search for latest changes if helpful"

### Partial Knowledge
When knowledge is incomplete but substantial:
- Share what's known with confidence level
- Search to fill specific gaps
- Synthesize both sources clearly

### User Correction
When user indicates provided information is wrong:
- Search immediately to verify
- Acknowledge if knowledge was outdated
- Update response with current information

## Related Protocols
- [[Error Recovery Protocol v1.2.0]] - When search fails or provides bad results
- [[Information Integration Protocol v1.2.0]] - Synthesizing multiple sources
- [[Architecture First Protocol v1.2.0]] - Checking docs before web search
- [[User Communication Protocol v1.2.0]] - How to communicate search decisions

## Success Metrics
- Reduced unnecessary searches for established knowledge
- Improved currency of information provided
- Better integration of internal tools with external search
- User receives optimal information source for their needs
- Faster response times through appropriate tool selection

## Examples

### Internal Tools → Knowledge → No Search Needed
**Query**: "How does our Brain initialization work?"
1. Check `mcp-architecture:arch_find_document "brain"`
2. Use existing knowledge of system
3. No search needed (internal system)

### Knowledge → Search for Verification
**Query**: "Is Python 3.12 still the latest version?"
1. Share known information about Python releases
2. Search for current Python version status
3. Synthesize both sources

### Immediate Search
**Query**: "What happened in the tech industry today?"
1. Search immediately (current events)
2. No need to check other sources first

## Version History
- **v1.0.0** (Aug 19, 2025): Initial creation based on observed search decision patterns

---

**Status**: Ready for testing and iteration  
**Philosophy**: Create systematic approach, refine through usage  
**Next**: Monitor effectiveness and adjust decision tree based on real usage patterns
