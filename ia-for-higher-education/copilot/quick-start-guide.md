# Quick Start Guide: Deploy in 30 Minutes

**Goal:** Get the Higher Ed IA Assistant running in Microsoft Copilot as fast as possible.

**Time Required:** ~30 minutes (minimal configuration)

---

## Prerequisites

- [ ] Microsoft Copilot or Copilot Studio account/access
- [ ] GitHub account (free tier is fine)
- [ ] The research report file: `higher-ed-ia-research-report.md`

---

## Step 1: GitHub Setup (10 minutes)

### Option A: Quick & Dirty (Fastest)
1. Go to https://github.com
2. Click "+" → "New repository"
3. Name it: `higher-ed-ia-knowledge`
4. Set to **Public**
5. Check "Add a README file"
6. Click "Create repository"
7. Click "Add file" → "Upload files"
8. Upload `higher-ed-ia-research-report.md`
9. Click "Commit changes"

### Get the Raw URL:
1. Click on `higher-ed-ia-research-report.md`
2. Click "Raw" button (top-right)
3. Copy URL from browser (it will look like):
   ```
   https://raw.githubusercontent.com/[your-username]/higher-ed-ia-knowledge/main/higher-ed-ia-research-report.md
   ```
4. **Test it:** Paste URL in new browser tab → Should show plain text
5. **Save this URL** (you'll need it in Step 2)

---

## Step 2: Copilot Configuration (15 minutes)

### A. Access Copilot Configuration

**Microsoft Copilot Studio:**
1. Go to https://copilotstudio.microsoft.com
2. Sign in
3. Click "Create" → "New agent" (or edit existing)
4. Go to agent settings/configuration

**Standard Microsoft Copilot:**
1. Open Copilot
2. Look for Settings/Preferences
3. Find "Custom Instructions" or similar
   *(Note: Feature availability varies by plan)*

### B. Add Instructions

1. Open `copilot-instructions.md` from this package
2. **Copy entire contents** (Ctrl+A, Ctrl+C)
3. **Paste into Copilot's instructions field**
4. Verify character count shows ~7,850 (under 8K limit)
5. **Save**

### C. Add Knowledge Source (Copilot Studio Only)

1. Find "Knowledge" section in agent settings
2. Click "Add knowledge" → "Public website"
3. Paste your GitHub raw URL from Step 1
4. Add name: "Higher Ed IA Research Report"
5. Add description: "Comprehensive research on higher education website information architecture best practices"
6. **Save**

*(If using standard Copilot without knowledge linking, skip this—instructions reference external sources which Copilot may fetch via search)*

### D. Add Conversation Starters (5 minutes)

Add these 4 prompts (from `suggested-prompts.md`):

**Prompt 1:**
- **Title:** "Plan IA for university website redesign"
- **Message:** "I'm working on redesigning our university website and need help planning the information architecture. Can you ask me some questions to understand our needs and then suggest some IA options?"

**Prompt 2:**
- **Title:** "Review my navigation structure"
- **Message:** "Can you review my proposed navigation structure for common IA problems, especially organizational structure issues and accessibility concerns?"

**Prompt 3:**
- **Title:** "What are the biggest IA mistakes in higher ed?"
- **Message:** "I'm new to information architecture for higher education websites. What are the most common mistakes university sites make?"

**Prompt 4:**
- **Title:** "Design IA for academic department site"
- **Message:** "I need to create information architecture for our academic department website. How should departmental IA differ from institutional IA?"

**Save all changes.**

---

## Step 3: Quick Test (5 minutes)

### Test 1: Basic Functionality
1. Start new conversation
2. Type: "Help me design IA for my university website"
3. **Expected:** Should ask 5+ clarifying questions
4. ✅ **Pass:** If asks questions  
   ❌ **Fail:** If immediately generates IA without questions

### Test 2: Anti-Pattern Detection
1. New conversation
2. Say: "Here's my navigation: College of Arts & Sciences | School of Business | College of Engineering"
3. **Expected:** Should flag this as organizational structure anti-pattern
4. ✅ **Pass:** If flags and explains why problematic  
   ❌ **Fail:** If accepts this structure without warning

### Test 3: Research Citation
1. New conversation
2. Ask: "What's the Top 4 Questions framework?"
3. **Expected:** Should explain framework and cite research (e.g., "Research Section 1.2")
4. ✅ **Pass:** If provides framework with citation  
   ❌ **Fail:** If explains without citing research

**If all 3 tests pass → You're good to go! 🎉**

---

## Troubleshooting Quick Fixes

### Problem: Not asking questions before generating IA
**Fix:** Add this at the very top of instructions:
```markdown
🚨 CRITICAL: ALWAYS ask 5-8 clarifying questions BEFORE generating any IA options.
NEVER generate IA without understanding context first.
```

### Problem: Not citing research
**Fix:** Add to Research Citation section:
```markdown
MANDATORY: Every recommendation must cite specific research sections.
Use format: "Research Section X.X shows..."
```

### Problem: Only generating 1 option instead of 2-3
**Fix:** Add emphasis in workflow:
```markdown
REQUIRED: Generate MINIMUM 2 options, preferably 3.
Each option must be distinct and genuinely viable.
```

### Problem: GitHub URL not accessible
**Fix:** Verify:
1. Repository is Public (not Private)
2. Using "raw" URL (not regular GitHub page)
3. File uploaded successfully
4. Try accessing URL in incognito/private browser window

---

## You're Done! What Now?

### Immediate Next Steps:

1. **Share with target users**
   - Give them the conversation starter prompts
   - Basic usage tips (see User Guide section below)

2. **Collect feedback**
   - What works well?
   - Where does it struggle?
   - What features would help?

3. **Iterate**
   - Refine instructions based on real usage
   - Update conversation starters
   - Enhance knowledge base

### User Guide (Share This)

**How to Use the Higher Ed IA Assistant:**

**Start a Conversation:**
- Use a suggested prompt (button)
- OR describe your project naturally

**Answer Questions:**
- The assistant will ask 5-8 clarifying questions
- Provide as much context as you can
- It's okay to say "I don't know" or "We're flexible"

**Review Options:**
- You'll get 2-3 distinct IA proposals
- Each has strengths, weaknesses, and best-use scenarios
- Compare them and pick what fits your needs

**Ask Follow-ups:**
- "Why did you recommend this?"
- "How would this work for [specific scenario]?"
- "Can you refine Option 2 to address [concern]?"

**Tips for Best Results:**
- Share your current navigation if redesigning
- Mention accessibility requirements upfront
- Be honest about political/stakeholder constraints
- Ask "why" to understand the reasoning

---

## Optional: Enhanced Setup (Do Later)

When you have more time, consider:

### Add More Knowledge Files
Create and upload to GitHub:
- `frameworks-quick-reference.md` - Distilled frameworks
- `examples-library-digest.md` - 5-10 key examples
- `accessibility-checklist.md` - WCAG 2.1 quick reference

### Create User Documentation
- How-to guide for your team
- FAQs about the assistant
- Examples of good prompts

### Set Up Analytics (Copilot Studio)
- Track usage patterns
- Identify common questions
- Measure satisfaction

### Build Custom Topics (Copilot Studio)
- Structured workflows for common tasks
- Entity recognition for institution types
- Integration with your tools

**But don't do this now—get the basic version working first!**

---

## Success Metrics

**Week 1:**
- [ ] 3+ users have tried it
- [ ] All 3 quick tests pass
- [ ] No major issues reported

**Month 1:**
- [ ] 10+ conversations completed
- [ ] Positive feedback from users
- [ ] At least 1 IA project used recommendations

**Quarter 1:**
- [ ] Regular usage by web team
- [ ] Measurable time savings
- [ ] Improved IA quality in projects

---

## Need Help?

### Resources in This Package:
- **Full details:** `deployment-checklist.md`
- **Troubleshooting:** `deployment-checklist.md` Step 7
- **Compression analysis:** `compression-analysis.md`
- **Implementation summary:** `implementation-summary.md`

### Common Issues → Quick Fixes:
| Issue | Fix Location |
|-------|--------------|
| Not asking questions | Instructions top |
| No research citations | Research Citation section |
| Only 1 option | Workflow Phase 2 |
| GitHub URL fails | Step 1 verification |

### Still Stuck?
1. Check Copilot Studio documentation
2. Verify all prerequisites met
3. Review test results for specific failures
4. Try with fresh conversation (clear context)

---

## Minimal Viable Deployment Checklist

- [ ] GitHub repo created with research report
- [ ] Raw URL obtained and tested in browser
- [ ] Instructions copied into Copilot
- [ ] 4 conversation starters added
- [ ] 3 quick tests passed
- [ ] Shared with first user

**That's it! You're deployed.** 🚀

Everything else in the full package is optional enhancement for later.

---

## Timeline Comparison

| Task | Full Deployment | Quick Start |
|------|----------------|-------------|
| GitHub setup | 15-30 min | 10 min |
| Copilot config | 30-45 min | 15 min |
| Testing | 15-30 min | 5 min |
| Documentation | 15-30 min | Skip for now |
| **Total** | **1.5-2.5 hours** | **30 minutes** |

**Quick Start gets you 80% of value in 20% of time.**

Do full deployment later when you have more time to optimize.

---

## What You're Skipping (Can Do Later)

**Skipping Now:**
- Comprehensive testing suite
- User documentation creation
- Version control setup
- Analytics configuration
- Advanced features

**But You Still Get:**
- Core IA consulting workflow
- Research-backed recommendations
- Anti-pattern detection
- Multiple option generation
- Accessibility integration

**You can always enhance later!**

---

## One-Liner Summary

**30 minutes to research-backed IA consulting assistant in Copilot: Upload research to GitHub → Copy instructions → Add 4 prompts → Test → Done.**

Now go deploy! 💪

---

**Created:** November 8, 2024  
**Purpose:** Get Doug up and running ASAP  
**Next:** See `deployment-checklist.md` for full deployment details
