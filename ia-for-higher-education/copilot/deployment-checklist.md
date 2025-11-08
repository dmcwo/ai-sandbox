# Deployment Checklist: Higher Education IA Assistant for Microsoft Copilot

## OVERVIEW

This guide walks you through setting up the Higher Education Information Architecture Planning Assistant in Microsoft Copilot (or Copilot Studio), working within the 8,000-character instruction limit.

**Architecture:** Three-tier system
1. **Core Instructions** (8,000 chars) → In Copilot "Instructions" field
2. **Knowledge Sources** (external) → Linked via public URLs
3. **Suggested Prompts** → In Copilot "Conversation Starters"

---

## STEP 1: Host Knowledge Files on GitHub

### 1.1 Create/Identify GitHub Repository

**Option A: Existing Repo**
Use an existing public repository where you can add documentation files.

**Option B: New Repo**
Create a dedicated repository (e.g., `higher-ed-ia-resources`) to host the knowledge base.

### 1.2 Upload Knowledge Files

Upload these files to your GitHub repository:

**Required Files:**
1. **`higher-ed-ia-research-report.md`** - The comprehensive research document (existing file)
2. **`frameworks-quick-reference.md`** - Optional: Distilled frameworks guide (can create if needed)
3. **`examples-library-digest.md`** - Optional: Key examples (can create if needed)

**File Organization Options:**

**Simple Structure:**
```
/repo-root/
  ├── higher-ed-ia-research-report.md
  └── README.md
```

**Organized Structure:**
```
/repo-root/
  ├── research/
  │   └── higher-ed-ia-research-report.md
  ├── frameworks/
  │   └── frameworks-quick-reference.md
  └── examples/
      └── examples-library-digest.md
```

### 1.3 Get Raw GitHub URLs

For each file, get the **raw** URL format:

**URL Format:**
```
https://raw.githubusercontent.com/[username]/[repo-name]/[branch]/[path-to-file]
```

**Example:**
```
https://raw.githubusercontent.com/dworsham/higher-ed-ia-resources/main/higher-ed-ia-research-report.md
```

**How to Get Raw URL:**
1. Navigate to file on GitHub
2. Click "Raw" button (top-right of file viewer)
3. Copy URL from browser address bar

### 1.4 Verify Accessibility

Test each raw URL in a browser to ensure:
- ✓ File loads as plain text markdown
- ✓ No authentication required (public repo)
- ✓ URL returns 200 OK status

---

## STEP 2: Configure Microsoft Copilot

### 2.1 Access Copilot Configuration

**Microsoft Copilot (Consumer/Basic):**
- Settings → Copilot → Custom Instructions (if available)

**Microsoft Copilot Studio (Enterprise):**
- Create new agent or edit existing
- Navigate to agent configuration

**Microsoft 365 Copilot (Enterprise):**
- May require Copilot Studio for custom agents
- Check with IT admin for permissions

### 2.2 Add Instructions

**Location:** Instructions or System Message field (varies by interface)

**Content:** Copy/paste the entire contents of `copilot-instructions.md`

**Verify:**
- ✓ Character count under 8,000
- ✓ Formatting preserved (markdown)
- ✓ No truncation

### 2.3 Add Knowledge Sources

**Method varies by Copilot version:**

**Copilot Studio:**
1. Navigate to "Knowledge" section
2. Select "Add knowledge" → "Public websites"
3. Add each raw GitHub URL
4. Provide descriptive names:
   - "Higher Ed IA Research Report"
   - "Frameworks Quick Reference" (if using)
   - "Examples Library" (if using)
5. Add descriptions (helps AI understand when to use each)

**Standard Copilot (if supported):**
- May need to reference URLs in instructions instead
- Include in "Knowledge Base" section if available

**Alternative (if direct knowledge linking not supported):**
Add to bottom of instructions:
```markdown
## KNOWLEDGE SOURCES

Reference these external documents when needed:
- Research Report: [URL]
- Frameworks: [URL]
- Examples: [URL]

Use web_search or file retrieval to access these when answering questions.
```

### 2.4 Add Conversation Starters

**Location:** "Suggested Prompts" or "Conversation Starters" field

**Add 4-6 prompts from `suggested-prompts.md`:**

**Recommended 6:**
1. "Help me plan IA for a university website redesign"
2. "Review my navigation structure for issues"
3. "What are the biggest IA mistakes in higher ed websites?"
4. "Design IA for an academic department website"
5. "Ensure our IA meets WCAG 2.1 AA accessibility standards"
6. "Balance user needs with internal politics in our IA"

**Format:**
- **Title:** Short, descriptive (shows as button)
- **Message:** Full prompt text (sent when clicked)

---

## STEP 3: Test & Validate

### 3.1 Basic Functionality Test

**Test 1: Clarifying Questions**
- Start: "Help me design IA for my university website"
- Expected: Should ask 5-8 clarifying questions before generating options
- ✓ Pass if questions asked
- ✗ Fail if immediately generates IA without context

**Test 2: Top 4 Questions Framework**
- Start: "What are the Top 4 Questions for a university homepage?"
- Expected: Should list the 4 questions and explain they need to be easily answerable
- ✓ Pass if correct framework cited

**Test 3: Anti-Pattern Detection**
- Provide: Navigation organized by colleges/departments
- Expected: Should flag organizational structure anti-pattern immediately
- ✓ Pass if flags and explains why it's problematic

**Test 4: Research Citation**
- Ask: "Why is topic-based navigation better than audience-based?"
- Expected: Should cite specific research sections (e.g., "Section 2.4")
- ✓ Pass if cites research; ✗ Fail if makes claims without citation

**Test 5: Multiple Options**
- Complete a full workflow (answer clarifying questions)
- Expected: Should generate 2-3 distinct, viable IA options
- ✓ Pass if provides options with strengths/weaknesses for each

### 3.2 Knowledge Source Verification

**Test with research-specific question:**
"What does the research say about the 3-click rule?"

**Expected Response:**
- Should reference that it's debunked (Research Section 7.2)
- Explain information scent matters more
- Cite specific research findings

**If fails:**
- Knowledge sources may not be properly linked
- Verify raw GitHub URLs are accessible
- Check knowledge source configuration in Copilot

### 3.3 Edge Cases

**Test 1: Out of Scope Request**
- Ask: "Can you design the visual mockups for our site?"
- Expected: Should politely explain this is outside IA scope

**Test 2: Incomplete Information**
- Provide vague request without details
- Expected: Should ask clarifying questions, not make assumptions

**Test 3: Accessibility Question**
- Ask specific WCAG 2.1 AA question
- Expected: Should reference accessibility guidelines accurately

---

## STEP 4: Refine Based on Testing

### Common Issues & Fixes

**Issue:** Not asking clarifying questions before generating IA
**Fix:** Strengthen Phase 1 emphasis in instructions:
```markdown
ALWAYS ASK 5-8 CLARIFYING QUESTIONS FIRST.
Never generate IA options without understanding context.
```

**Issue:** Not citing research sections
**Fix:** Add to top of instructions:
```markdown
🚨 CRITICAL: Always cite research using format "Research Section X.X shows..."
Never make claims without specific citations.
```

**Issue:** Generating only 1 option instead of 2-3
**Fix:** Emphasize in instructions:
```markdown
REQUIRED: Generate minimum 2 options, preferably 3.
Each option must be genuinely viable (not straw men).
```

**Issue:** Knowledge sources not being accessed
**Fix:** In instructions, explicitly reference:
```markdown
Before answering, check external knowledge sources:
[List URLs with descriptions of when to use each]
```

---

## STEP 5: Documentation & Handoff

### 5.1 Create Usage Guide for End Users

**Include:**
- How to access the assistant
- What it can/cannot do
- How to ask good questions (provide context)
- What to have ready (sitemaps, analytics, etc.)
- Suggested prompts reference

**Sample User Guide Template:**
```markdown
# Using the Higher Ed IA Planning Assistant

## What It Does
This AI assistant helps you plan information architecture 
for university websites based on research-backed best practices.

## How to Use It
1. Start with a suggested prompt OR describe your project
2. Answer clarifying questions it asks
3. Review 2-3 IA options it generates
4. Ask follow-up questions to refine

## Tips for Best Results
- Provide context (site type, users, constraints)
- Share analytics/sitemaps if redesigning
- Be honest about political constraints
- Ask "why" to understand recommendations

## What to Have Ready
- Current navigation structure (if redesigning)
- User personas or primary audiences
- Top goals for the site
- Any accessibility or compliance requirements
```

### 5.2 Version Control

**Track what you deployed:**
- Date deployed
- Instructions version (e.g., v1.0)
- Knowledge source URLs
- Any customizations made

**Create changelog for future updates:**
```markdown
## v1.0 (2024-11-08)
- Initial deployment
- Instructions: copilot-instructions.md
- Knowledge: higher-ed-ia-research-report.md
- Prompts: 6 conversation starters

## v1.1 (Future)
- [Track changes here]
```

---

## STEP 6: Ongoing Maintenance

### Regular Checks (Monthly)

**Test Functionality:**
- Run through 5 basic tests (Step 3.1)
- Verify knowledge sources still accessible
- Check for any Copilot platform updates affecting behavior

**Update Knowledge:**
- New research findings?
- Industry best practices evolved?
- Regulatory changes (accessibility deadlines)?

**Refresh Examples:**
- Add new case studies
- Update examples-library with real projects

### Feedback Loop

**Collect from users:**
- What questions does it answer well?
- Where does it struggle?
- What features would improve it?

**Iterate instructions:**
- Strengthen weak areas
- Add examples for common misunderstandings
- Refine prompts based on actual usage patterns

---

## TROUBLESHOOTING GUIDE

### Problem: Assistant isn't asking questions before generating IA

**Diagnosis:** Instructions not emphasizing workflow enough  
**Fix:** Add ALL CAPS reminders at start of Phase 1

### Problem: Research citations missing or incorrect

**Diagnosis:** Knowledge sources not properly linked OR instructions unclear  
**Fix:** 
1. Verify GitHub URLs accessible
2. Add explicit citation protocol to instructions
3. Test: Ask research-specific question and verify citation

### Problem: Generating only generic advice, not customized

**Diagnosis:** Not gathering enough context  
**Fix:** Expand clarifying questions list in instructions

### Problem: Ignoring accessibility requirements

**Diagnosis:** Accessibility not prioritized in instructions  
**Fix:** Move accessibility to critical constraints section, add WCAG checklist

### Problem: Suggesting organizational structure (anti-pattern)

**Diagnosis:** Anti-pattern warning not strong enough  
**Fix:** 
1. Make anti-pattern section more prominent
2. Add examples of bad vs. good structure
3. Create explicit "Never Do" list

---

## ADVANCED: Copilot Studio Specific Features

If using Copilot Studio (enterprise version), you can enhance with:

### Topics & Flows
Create structured conversation flows for:
- Redesign analysis workflow
- New site planning workflow
- IA review workflow

### Entities
Define custom entities:
- Institution types
- Site types  
- User personas
- Accessibility levels

### Analytics
Track:
- Most common questions
- Where users get stuck
- Most requested features
- Satisfaction ratings

### Plugins & Actions
Integrate with:
- Analytics platforms (to pull real data)
- Sitemap generators
- Accessibility testing tools

---

## SUCCESS METRICS

Track these to measure effectiveness:

**Usage Metrics:**
- Number of conversations started
- Completion rate (full workflow to IA options)
- Return users vs. new users

**Quality Metrics:**
- User satisfaction ratings
- Number of follow-up questions needed
- IA options that users actually implement

**Impact Metrics:**
- Time saved vs. manual IA planning
- Improved accessibility compliance
- Reduced stakeholder conflicts
- Better user testing results

---

## APPENDIX: Platform-Specific Notes

### Microsoft Copilot (Consumer)
- Limited customization options
- May not support external knowledge sources directly
- Focus on comprehensive instructions with examples

### Microsoft 365 Copilot (Enterprise)
- May require Copilot Studio for full customization
- Check licensing requirements
- Coordinate with IT/admin

### Copilot Studio (Full Platform)
- Most flexible and powerful option
- Supports all features in this guide
- Requires additional setup and licensing

---

## QUICK START CHECKLIST

- [ ] GitHub repo created with knowledge files
- [ ] Raw URLs verified and accessible
- [ ] Instructions copied into Copilot (under 8K chars)
- [ ] Knowledge sources linked (if supported)
- [ ] 6 conversation starters added
- [ ] 5 basic functionality tests passed
- [ ] Research citation test passed
- [ ] User guide created
- [ ] Deployment documented
- [ ] Feedback collection method established

**Estimated Setup Time:** 1-2 hours for initial deployment

---

**Good luck with your deployment! 🎉**

For questions or issues, refer to troubleshooting section or consult Copilot Studio documentation.
