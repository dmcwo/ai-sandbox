# frameworks-guide.md

## 1. Introduction to Prompting Frameworks

Effective AI prompt engineering relies on structured frameworks to design clear, accurate, and context-sensitive instructions. This guide covers five core, evidence-backed frameworks: TCEPFT, COOP/COOPET, KERNEL, RTF, and CARE, enabling precise prompt creation tailored to task complexity and user expertise.

***

## 2. TCEPFT Framework

### 2.1 Overview  
TCEPFT emphasizes Task, Context, Example, Persona, Format, and Tone to deliver detailed, domain-specific instructions.

### 2.2 Components  
- Task: Define GPT actions.  
- Context: Background knowledge and constraints.  
- Example: Input-output samples.  
- Persona: Role and style.  
- Format: Output structure.  
- Tone: Communication style.

### 2.3 Use Cases  
Complex, regulatory, or expert-level tasks.

### 2.4 Evidence  
* Improves accuracy up to 60% over unstructured prompts (Sahoo et al., 2024). 
* Goal-aligned, example-rich prompts reduce accuracy errors by 28% (Frontiers in Medicine, 2025)

***

## 3. COOP and COOPET Frameworks

### 3.1 Overview  
COOP (Context, Objective, Operation, Persona) and COOPET (adds Example, Tone) support straightforward, iterative instructions with simplicity.

### 3.2 Components  
- Context: Input and background information.  
- Objective: Clear goal or function.  
- Operation: How the GPT processes inputs and what it produces.  
- Persona: Communication style and role.  
- Example (COOPET only): Sample input-output pairs.  
- Tone (COOPET only): Communication tone.

### 3.3 Use Cases  
Beginners, rapid iteration, evolving tasks.

### 3.4 Evidence  
Enhances development speed and adaptability (Sahoo et al., 2024). Simplified frameworks like COOP are highly effective for single-purpose tasks (MIT COLI, 2024). Adding Examples and Tone (COOPET) increases consistency and reduces hallucinations.

***

## 4. KERNEL Framework

### 4.1 Overview  
Modular prompts emphasizing Knowledge, Execution, Reasoning, Exchange, and Learning for technical workflows.

### 4.2 Components  
- Knowledge: Explicit domain facts and data.  
- Execution: Clear commands and actions.  
- Reasoning: Stepwise logic or justifications.  
- Exchange: Multi-turn interactions and clarifications.  
- Learning: Adaptive instruction from previous outputs.

### 4.3 Use Cases  
Technical documentation, privacy-sensitive, multi-turn reasoning.

### 4.4 Evidence
Emphasizes modularity and separation of concerns, reducing hallucinations by 34–59% (Endor Labs, 2025).

***

## 5. RTF Framework

### 5.1 Overview  
Minimal Role, Task, Format for agile prototyping.

### 5.2 Components  
- Role: Actor or persona.  
- Task: Specific action or goal.  
- Format: Expected output structure.

### 5.3 Use Cases  
Low complexity, quick testing, informal tasks.

**Evidence Base:** Minimal but effective for straightforward applications. Scalable upward by adding examples and tone when complexity increases.

***

## 6. CARE Framework

### 6.1 Overview  
Focuses on Context, Action, Role, Expectation for clear, goal-oriented prompts.

### 6.2 Components  
- Context: Background information.  
- Action: What needs to be done.  
- Role: Responsible actor or system.  
- Expectation: Desired outcome or quality.

### 6.3 Use Cases  
Managerial tasks requiring concise roles and outcomes.

***

## 7. Critical Instruction Components

- Role and expertise
- Clear task and goals  
- Persona and tone  
- Context and constraints  
- Example-driven guidance with clear labels (e.g., "Good example", "Poor Example") and diverse scenarios (e.g., "Simple", "Complex", "Edge Case")  
- Output format specification  
- Ethical and legal guardrails including what NOT to do, topics or content to avoid, domain boundaries, safety guidelines

***

## 8. Proven Prompting Techniques

- Chain-of-thought prompting  
- Few-shot examples: Provide 2–3 input-output examples before asking for new output.  
- Role-based perspectives  
- Structured output templates: Specify exact output format using XML tags, JSON, markdown, or lists.
- Explicit constraints

***

## 9. Common Anti-Patterns to AVOID

- Overloading tasks  
- Vague instructions  
- Mixed personas  
- Skipping validation
- Contradictions Across Sections
- Token Waste: Bloated Instructions


***

## 10. Instruction Optimization Checklist

- Is the task clear?  
- Is context sufficient?  
- Are persona and tone explicit?  
- Are examples relevant?  
- Is output format precise?  
- Are anti-patterns avoided?  
- Is validation included?
- Is it efficient?


***

## 11. References

- Sahoo et al., 2024; Frontiers in Medicine, 2025; Fabio Vivas, 2025; Parloa, 2025; Key prompt engineering studies.

- Endor Labs. (2025). Anti-pattern avoidance: A simple prompt pattern for safer AI-generated code. Retrieved from https://www.endorlabs.com/learn/anti-pattern-avoidance-a-simple-prompt-pattern-for-safer-ai-generated-code

- Frontiers in Medicine. (2025). A guide to prompt design: Foundations and applications. Retrieved from https://www.frontiersin.org/journals/medicine/articles/10.3389/fmed.2024.1504532/full

- MIT COLI (Computational Linguistics). (2024). Large language model instruction following: A survey. Retrieved from https://direct.mit.edu/coli/article/50/3/1053/121669

- Parloa. (2025). Everything you need to know about prompt engineering frameworks. Retrieved from https://www.parloa.com/knowledge-hub/prompt-engineering-frameworks/

- Sahoo, P., Singh, A. K., Saha, S., Jain, V., Mondal, S., & Chadha, A. (2024). A systematic survey of prompt engineering in large language models: Techniques and applications. Retrieved from https://arxiv.org/abs/2402.07927

- Wei, J., et al. (2022). Chain-of-thought prompting elicits reasoning in large language models. ArXiv preprint arXiv:2201.11903.

- (https://www.reddit.com/r/PromptEngineering/comments/1kbufy0/the_ultimate_prompt_engineering_framework/)
- (https://platform.openai.com/docs/guides/prompt-engineering)
- (https://arxiv.org/pdf/2109.01134.pdf)
- (https://www.promptingguide.ai/introduction/elements)
- (https://www.linkedin.com/posts/sandeep-burman_writing-better-prompts-by-applying-the-core-activity-7374414945037279233-W0rW)
- (https://learn.microsoft.com/en-us/azure/ai-foundry/openai/concepts/prompt-engineering)
- (https://www.sciencedirect.com/science/article/pii/S2666389925001084)
- (https://openaccess.thecvf.com/content/CVPR2022/papers/Zhou_Conditional_Prompt_Learning_for_Vision-Language_Models_CVPR_2022_paper.pdf)