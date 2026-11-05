# Required paper: Lost in the Middle

**Liu, N. F., Lin, K., Hewitt, J., Paranjape, A., Bevilacqua, M., Petroni, F., & Liang, P. (2023). *Lost in the Middle: How Language Models Use Long Contexts*.** [arXiv:2307.03172](https://arxiv.org/abs/2307.03172) · [PDF](https://arxiv.org/pdf/2307.03172)

This is the one paper you must read for the midterm. Plan for about an hour.

## Why this paper

It is a short, controlled experiment with one clear result, and that result explains much of what the course says about working with agents:

- **Week 3:** the context window is a budget, and a longer window does not mean the model attends to all of it equally.
- **Context Management:** the reason to *manage* context (load it when needed, keep it short, put key facts at the start or end) instead of stuffing everything in.
- **Codebase Structure:** why every line of `AGENTS.md`, a rule or a tool description competes for attention, and why long context files can fail to help.

## What to know

- **The question.** When the information a model needs sits at different positions in a long input, does the model use it equally well?
- **The method.** Two tasks: multi-document question answering (one document holds the answer, the rest are distractors) and synthetic key-value retrieval. The authors move the relevant item to different positions and vary the input length, across several models.
- **The finding.** Accuracy follows a **U-shaped curve**: highest when the relevant information is at the **start or the end** of the input, and it drops when it is in the **middle**. In some settings, a model given the answer in the middle did worse than with no documents at all.
- **Longer windows do not fix it.** Models with extended context windows showed the same pattern. A larger window raises how much fits, not how well the middle is used.
- **The kind of evidence.** A controlled experiment on retrieval-style tasks. Be able to say what it shows (position affects use of information) and where it might not apply (other tasks, newer models, real coding sessions).

## Connect it to practice

- Put the instructions that matter most at the start or the end of a prompt, and restate key rules when a session gets long.
- Load context when the task needs it instead of up front.
- When an agent ignores a constraint, one of the checks is *where it sat* in the context.

## Check yourself

1. What shape does accuracy take as the relevant passage moves through the input?
2. Did models with longer context windows avoid the problem?
3. What kind of evidence is this, and name one setting where you would be careful about applying it.

---

[Back to the study guide index](README.md)
