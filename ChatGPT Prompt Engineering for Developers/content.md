# ChatGPT Prompt Engineering for Developers

They are 2 types of Large language models(llm)
1. Base llm - Predict next word, based on text training data
2. Instruction Tuned llm - Tries to follow instruction, Fine-Tune on instruction, use RLHF-reinforcement learning using human feedback

## Principles of Prompting

1. Principle: Write clear and specific instruction (clear!=short)
    - Tactic 1: 
        - Triple quotes: """
        - Triple backticks: ```
        - Triple dashes: ---
        - Angle brackets: <>
        - XML tags: <tag></tag>
    - Tactic 2: Ask for structured output HTML, JSON
    - Tactic 3: Check whether conditions are satisfied,Check assumptions required to do the task(here we give condition based work)
    - Tactic 4: Few-shot prompting-Give successful examples of completing tasks then ask model to perform the task
2. Principle: Give the model time to think
    - Tactic 1: Specify the steps to complete a task
    - Tactic 2: Instruct the model to work out its own solution before rushing to a conclusion
3. Principle: Model Limitations
    - Hallucination-makes statements that sound plausible but are not true
    - Reducing hallucinations-First find relevant information, then answer the question based on the relevant information

## Iterative Process
- Try something
- Analyze where the result does not give what you want
- Clarify instructions, give more time to think
- Refine prompts with a batch of examples