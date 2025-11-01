# Web Search Decision Protocol v1.0.0
*Created: August 20, 2025*  
*Type: Foundation Protocol (Tier 2)*  
*Purpose: Systematic decision framework for when to use web search vs other information sources*

## Overview
This protocol provides a systematic decision tree for determining when to use web search tools versus other information sources (Brain, knowledge base, internal tools). Prevents inefficient information gathering and ensures appropriate tool selection.

## Triggers
- User asks about unknown terms, concepts, or entities
- Information request involves current/recent events (post-January 2025)
- Need to verify or update knowledge claims
- Searching for real-time data (prices, news, status)
- User explicitly requests "search" or "look up"
- Encountering unfamiliar acronyms, product names, or technical terms

## Decision Framework

### 1. Unknown Terms/Entities
**IMMEDIATE WEB SEARCH if:**
- Term is completely unknown to Claude
- Acronym or technical term not in knowledge base
- Proper nouns (people, places, products) not recognized
- New technology or recent developments

**Example**: User mentions "MXFP4" → Immediate web search

### 2. Temporal Considerations  
**WEB SEARCH REQUIRED for:**
- Current events or news (daily/weekly updates)
- Real-time data (stock prices, weather, sports scores)
- Recent developments in fast-moving fields
- Information that changes monthly or more frequently

**KNOWLEDGE BASE SUFFICIENT for:**
- Historical facts and established knowledge
- Scientific principles and mathematical concepts
- Literature, arts, and stable cultural knowledge
- Information that changes yearly or less frequently

### 3. Verification and Updates
**WEB SEARCH when:**
- User asks to "verify" information
- Claims need current confirmation
- User indicates they have newer information
- Conflicting information needs resolution

### 4. User Intent Signals
**Search immediately if user says:**
- "What is [unknown term]?"
- "Look up [anything]"
- "Find information about..."
- "What's the latest on..."
- "Current status of..."

## Step-by-Step Procedure

### Step 1: Quick Recognition Check
```
Ask yourself: "Do I know what this term/concept means?"
- YES → Proceed to Step 2
- NO → IMMEDIATE WEB SEARCH
```

### Step 2: Temporal Assessment
```
Ask: "Is this information likely to have changed since January 2025?"
- YES → WEB SEARCH
- NO → Use knowledge base, proceed to Step 3
```

### Step 3: User Intent Analysis
```
Ask: "Is the user asking for verification or current information?"
- YES → WEB SEARCH
- NO → Use knowledge base, offer to search for updates
```

## Tools and Commands

### Primary Search Tool
```
web_search
- query: "search terms"
```

### Alternative Search Tool (if available)
```
tracked-search:web_search
- query: "search terms" 
```

### Follow-up Tool
```
web_fetch
- url: "specific URL from search results"
```

## Search Query Optimization

### Good Search Queries
- 1-6 words for best results
- Start broad, then narrow if needed
- Use specific terms when possible
- Include year/date for recent events

### Examples
- "MXFP4" (perfect - specific unknown term)
- "OpenAI GPT-OSS 2025" (good - specific recent development)
- "Python tutorial" (too broad - needs specification)

## Common Patterns

### Pattern 1: Unknown Technical Terms
**Trigger**: User mentions unfamiliar acronym/term
**Action**: Immediate web search
**Example**: "MXFP4" → web_search("MXFP4")

### Pattern 2: Current Events
**Trigger**: User asks about recent news/developments
**Action**: Web search with temporal qualifiers
**Example**: "latest AI developments" → web_search("AI developments 2025")

### Pattern 3: Verification Requests
**Trigger**: User asks to confirm information
**Action**: Search for current authoritative sources
**Example**: "Is this still accurate?" → web_search(specific claim)

## Anti-Patterns to Avoid

❌ **Searching for basic knowledge** (Python syntax, historical facts)
❌ **Multiple similar searches** (vary query terms instead)
❌ **Searching instead of asking clarifying questions**
❌ **Using overly broad or narrow search terms**
❌ **Forgetting to search for genuinely unknown terms**

## Integration with Other Protocols

### Related Protocols
- **Task Approach Protocol**: Use for intent analysis before searching
- **Information Integration Protocol**: Use after gathering multiple sources
- **Error Recovery Protocol**: Use when searches fail or return poor results

### Brain System Integration
- Always check Brain first with brain_recall() for known information
- Store search results in Brain memory when useful
- Update smarts with frequently needed information

## Quality Standards

### Good Search Decision
- [ ] Correctly identified unknown vs known information
- [ ] Appropriate temporal assessment
- [ ] Used optimal search terms
- [ ] Found relevant, authoritative sources
- [ ] Integrated results effectively

### Success Metrics
- User gets accurate, current information
- No wasted searches on known information
- Quick resolution of unknown terms
- Effective source quality and relevance

## Examples from Real Usage

### Example 1: Unknown Term (Success)
**User Input**: "What is MXFP4?"
**Decision**: Unknown term → Immediate web search
**Query**: "MXFP4"
**Result**: Found comprehensive technical information
**Outcome**: ✅ Perfect - efficient resolution of unknown term

### Example 2: Known Information (Correct Restraint)
**User Input**: "What's the capital of France?"
**Decision**: Basic knowledge → No search needed
**Response**: Direct answer from knowledge base
**Outcome**: ✅ Correct - avoided unnecessary search

## Edge Cases

### Case 1: Partially Known Terms
If term is somewhat familiar but context suggests newer development:
- Make initial assessment from knowledge
- Mention uncertainty
- Offer to search for latest information

### Case 2: Ambiguous Requests  
If unclear whether search is needed:
- Provide knowledge-based answer
- Explicitly offer to search for current information
- Let user decide

## Version History
- v1.0.0 (August 20, 2025): Initial creation based on observed search decision patterns

## Related Protocols
- [[Task Approach Protocol v1.2.0]] - For initial request analysis
- [[Information Integration Protocol v1.2.0]] - For synthesizing search results
- [[User Communication Protocol v1.2.0]] - For explaining search decisions

---

**Status**: Active Foundation Protocol
**Next Review**: After 2 weeks of usage
**Integration**: Ready for brain_init_v5_working inclusion
