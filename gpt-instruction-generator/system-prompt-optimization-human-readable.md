## System Prompt Optimization Framework

### 1. Goal & Context Definition

- Explicitly state the task’s objective, target audience, and context to guide relevant reasoning.[4][5]
- Adopt a structure (e.g., CARE, TCEPFT, COOP, KERNEL, RTF) suited to required detail and domain.[5][6]

***

### 2. Input Granularity & Scope Control

- Use concise wording to minimize token usage without sacrificing clarity.[8][1]
- Scope instructions narrowly; specify boundaries for depth, length, and elaboration per turn.

***

### 3. Adaptive Inquiry & User Engagement

- Build in adaptive checks: clarify ambiguous input, pause after key steps, and seek explicit user permission before large-scale analysis or follow-ups.[4]
- Employ conditional logic: change depth and style based on user cues, with clear signals for stopping/continuing.[10][11]

***

### 4. Contextual Enhancement via Knowledge Base (if available)

- Integrate a retrievable knowledge base to streamline prompts, improve factuality, and enable updates without prompt rewrites.[12][13]
- For prompt-only systems, periodically audit for outdated info and optimize for brevity.[14][12]

***

### 5. Structure & Framework Application

- Choose an established framework (CARE, TCEPFT, COOP, KERNEL, RTF) fitting your workflow:  
  - Use CARE/TCEPFT for clarity and rule compliance.[15][16]
  - Use KERNEL/RTF for quick, minimalist prompting.[17][18]
  - Use COOP for detailed stepwise processes.[19]

***

### 6. Iterative Feedback & Continuous Optimization

- Implement feedback loops: solicit and log user responses, measure system prompt effectiveness, and refine based on error and resource usage data.[6][5][4]
- Use automated optimization/chaining tools when available for scalability and systematic improvement.[7][5][6]

***

### 7. Output Effectiveness & Evaluation

- Track metrics for accuracy, completeness, consistency, token efficiency, latency, and safety in real-world tests.[5][6][4]
- Regularly A/B test and review prompt variants against evolving requirements.

***

### Core Framework Flow

1. Explicit objective/context →  
2. Concise, scoped instructions →  
3. Adaptive inquiry logic & check-ins →  
4. Dynamic/contextual knowledge integration →  
5. Structured frameworks for clarity →  
6. Automated/feedback refinement →  
7. Output metrics & continuous review

***

This framework yields system prompts that are clear, efficient, and tuned for resource-aware, user-centered, and evidence-driven outcomes.[9][1][6][8][4][5]

[1](https://galileo.ai/blog/advanced-prompt-optimization-techniques-better-ai-results)
[2](https://help.openai.com/en/articles/6654000-best-practices-for-prompt-engineering-with-the-openai-api)
[3](https://www.reddit.com/r/ChatGPTPromptGenius/comments/1nytjzy/best_practices_for_ai_prompting_2025/)
[4](https://www.braintrust.dev/articles/systematic-prompt-engineering)
[5](https://orq.ai/blog/prompt-optimization)
[6](https://arize.com/blog/prompt-optimization-few-shot-prompting/)
[7](https://docs.aws.amazon.com/prescriptive-guidance/latest/gen-ai-lifecycle-operational-excellence/dev-experimenting-prompt-optimization.html)
[8](https://mitsloanedtech.mit.edu/ai/basics/effective-prompts/)
[9](https://cloud.google.com/discover/what-is-prompt-engineering)
[10](https://www.reddit.com/r/PromptEngineering/comments/1j250g9/the_latest_breakthroughs_in_ai_prompt_engineering/)
[11](https://pmc.ncbi.nlm.nih.gov/articles/PMC12109289/)
[12](https://www.chatbees.ai/blog/gpt-knowledge-base)
[13](https://docs.gpt4business.ai/getting-started/knowledge-base)
[14](https://www.eesel.ai/blog/knowledge-base-gpt)
[15](https://www.nngroup.com/articles/careful-prompts/)
[16](https://pmc.ncbi.nlm.nih.gov/articles/PMC12058339/)
[17](https://cybercorsairs.com/the-kernel-prompting-framework/)
[18](https://juuzt.ai/knowledge-base/prompt-frameworks/the-rtf-framework/)
[19](https://arxiv.org/abs/2203.05557)