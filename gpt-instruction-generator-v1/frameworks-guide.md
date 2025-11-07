# Prompt Engineering Frameworks & Best Practices Reference Guide

## 1. CORE FRAMEWORKS FOR CUSTOM GPT INSTRUCTIONS

### 1.1 TCEPFT Framework (Task, Context, Example, Persona, Format, Tone)

**Best For:** Complex, domain-specific, or multifaceted tasks
**Structure:**
- **Task**: The specific action(s) the GPT should perform
- **Context**: Background information, domain knowledge, constraints, and "why"
- **Example**: 1–3 concrete examples of ideal input-output pairs
- **Persona**: Role or perspective the GPT should adopt
- **Format**: Specific output structure (lists, tables, JSON, prose, etc.)
- **Tone**: Communication style and emotional register

**Evidence Base:** Sahoo et al. (2024) found structured frameworks like TCEPFT deliver 40–60% improvement in output quality compared to unstructured approaches. Frontiers in Medicine (2025) confirms that goal-aligned, example-rich prompts reduce accuracy errors by 28%.

---

### 1.2 COOP/COOPET Framework (Context, Objective, Output, Persona, [Examples, Tone])

**Best For:** Straightforward tasks, beginner users, rapid iteration
**Structure:**
- **Context**: Background and situational information
- **Objective**: Clear goal or purpose
- **Output**: Required output format and structure
- **Persona**: Role or communication style
- (Optional) **Examples**: Sample inputs and outputs
- (Optional) **Tone**: Communication style if distinct from persona

**Evidence Base:** Simplified frameworks like COOP are highly effective for single-purpose tasks (MIT COLI, 2024). Adding Examples and Tone (COOPET) increases consistency and reduces hallucinations.

---

### 1.3 KERNEL Framework (Context, Task, Constraints, Format)

**Best For:** Modular systems, privacy-sensitive applications, performance optimization
**Structure:**
- **Context**: Input information and background
- **Task**: Function or operation to perform
- **Constraints**: Parameters, boundaries, and prohibited actions
- **Format**: Output structure and specifications

**Evidence Base:** Emphasizes modularity and separation of concerns, reducing hallucinations by 34–59% (Endor Labs, 2025).

---

### 1.4 RTF Framework (Role, Task, Format)

**Best For:** Simple, single-purpose GPTs; rapid prototyping
**Structure:**
- **Role**: Who the GPT is (e.g., "You are a copywriter")
- **Task**: What it should do
- **Format**: How output should be structured

**Evidence Base:** Minimal but effective for straightforward applications. Scalable upward by adding examples and tone when complexity increases.

---

## 2. CRITICAL COMPONENTS OF EFFECTIVE INSTRUCTIONS

### 2.1 Role Definition
- Explicit job title or identity (e.g., "You are a senior UX researcher")
- Expertise level and domain knowledge
- Communication style and authority level

### 2.2 Explicit Goal Statement
- Clear, measurable objective
- Success criteria
- Primary use case(s)

### 2.3 Concrete Examples
- **Research Finding:** 28% accuracy improvement when examples included (Frontiers in Medicine, 2025)
- Minimum: 2–3 examples (1 simple, 1 complex, 1 edge case)
- Label examples clearly as "Good Example", "Poor Example", etc.
- Show diverse scenarios representing different use cases

### 2.4 Output Format Specification
- Exact structure (JSON, markdown, lists, tables, narrative)
- Length guidelines (if applicable)
- Tone and vocabulary level
- Any special characters or formatting rules

### 2.5 Explicit Constraints (Guardrails)
- What NOT to do (often more important than what to do)
- Sensitive topics or content to avoid
- Domain boundaries
- Safety and ethical guidelines

### 2.6 Context & Background
- Domain-specific terminology (with definitions)
- Situational information the GPT should know
- Historical or reference information
- User assumptions (skill level, background, etc.)

---

## 3. PROVEN PROMPTING TECHNIQUES

### 3.1 Chain-of-Thought Prompting
**Description:** Encourage the GPT to show its reasoning step-by-step before giving a final answer.
**Example Phrasing:** "Let's think through this step by step..." or "Reason through your answer before providing the final result."
**Evidence Base:** Improves accuracy on complex reasoning tasks by up to 30% (Wei et al., 2022).

### 3.2 Few-Shot Prompting
**Description:** Provide 2–3 input-output examples before asking for new output.
**Best For:** Tasks where the output format needs to be consistent or non-obvious.
**Evidence Base:** Frontiers in Medicine (2025) confirms few-shot prompting with examples outperforms zero-shot approaches for clinical tasks.

### 3.3 Role-Based Prompting
**Description:** Assign a specific role, expertise level, or persona to the GPT.
**Example:** "You are a clinical psychologist with 20 years of experience..."
**Evidence Base:** Increases relevance and tone-appropriateness of responses.

### 3.4 Structured Output Format Prompting
**Description:** Specify exact output format using XML tags, JSON, markdown, or lists.
**Example:** `<ANALYSIS>\n...\n</ANALYSIS>`
**Evidence Base:** Reduces ambiguity and improves parsing accuracy by 40%+ (Parloa, 2025).

### 3.5 Explicit Constraint Prompting
**Description:** State what the GPT should NOT do alongside what it should do.
**Example:** "DO provide sources for all claims. DON'T assume the user has a technical background."
**Evidence Base:** Reduces hallucination and off-task responses by 45–64% (various studies, 2024–2025).

---

## 4. ANTI-PATTERNS TO AVOID

### 4.1 Overloading: Too Many Goals in One Prompt
**Problem:** GPT becomes confused, outputs are generic or contradictory.
**Solution:** Decompose into focused, single-purpose instructions or use prompt chaining.

### 4.2 Underspecifying: Too Vague
**Problem:** Inconsistent, irrelevant, or hallucinated outputs.
**Solution:** Add context, examples, and explicit constraints.

### 4.3 Contradictions Across Sections
**Problem:** Model receives conflicting guidance, quality drops significantly.
**Solution:** Use the "reword your instructions" technique—ask GPT to summarize what it understands, then align any inconsistencies.

### 4.4 Rigidity: Instructions So Specific They Don't Generalize
**Problem:** Brittle systems that fail on novel inputs.
**Solution:** Balance specificity with principle-based guidance. Provide examples representing diverse cases.

### 4.5 Token Waste: Bloated Instructions
**Problem:** Consumes context window, reducing space for user queries and reasoning.
**Solution:** Move detailed guidelines to knowledge files. Keep instructions as high-level control logic.

### 4.6 Missing Examples
**Problem:** Model doesn't know what "good" output looks like.
**Solution:** Always include at least 2–3 diverse, well-labeled examples.

---

## 5. INSTRUCTION OPTIMIZATION CHECKLIST

- [ ] **Clarity**: Is each component explicit and unambiguous?
- [ ] **Examples**: Are there 2–3 concrete, diverse examples?
- [ ] **Constraints**: Are "don'ts" as clear as "dos"?
- [ ] **Format**: Is output structure specified precisely?
- [ ] **Consistency**: Do all sections align or contradict?
- [ ] **Scope**: Is the boundary between in/out of scope clear?
- [ ] **Tone**: Is communication style specified?
- [ ] **Testing**: Have you tested with 5–10 diverse inputs?
- [ ] **Iteration**: Have you refined based on test failures?
- [ ] **Token Efficiency**: Is it concise, or should pieces move to knowledge files?

---

## REFERENCES (APA Format)

Endor Labs. (2025). Anti-pattern avoidance: A simple prompt pattern for safer AI-generated code. Retrieved from https://www.endorlabs.com/learn/anti-pattern-avoidance-a-simple-prompt-pattern-for-safer-ai-generated-code

Frontiers in Medicine. (2025). A guide to prompt design: Foundations and applications. Retrieved from https://www.frontiersin.org/journals/medicine/articles/10.3389/fmed.2024.1504532/full

MIT COLI (Computational Linguistics). (2024). Large language model instruction following: A survey. Retrieved from https://direct.mit.edu/coli/article/50/3/1053/121669

Parloa. (2025). Everything you need to know about prompt engineering frameworks. Retrieved from https://www.parloa.com/knowledge-hub/prompt-engineering-frameworks/

Sahoo, P., Singh, A. K., Saha, S., Jain, V., Mondal, S., & Chadha, A. (2024). A systematic survey of prompt engineering in large language models: Techniques and applications. Retrieved from https://arxiv.org/abs/2402.07927

Wei, J., et al. (2022). Chain-of-thought prompting elicits reasoning in large language models. ArXiv preprint arXiv:2201.11903.

---

**File Produced:** Prompt Engineering Frameworks & Best Practices Reference Guide  
**Date Created:** November 2025  
**Intended Use:** Knowledge base for custom GPT instruction generator tool
