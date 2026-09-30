# Testing Prompt Injection

Through this project, I am stepping into the realm of AI Security. With the increase of AI models across multiple organizations, the risk of confidential data being leaked to threat actors is paramount. An LLM application typically has a **system prompt** (developer instructing it to never reveal certain data) and **user input** (whatever the user types in the box). Unfortunately, the system prompt AND the user input get fed into the model as one chunk of text. The model is not capable of differentiating between "trusted instruction" from the developer and "untrusted input" from the threat actor. If the user input *resembles* an instruction, the model will get confused. 

The current implementation of this project is an early stage Proof-of-Concept (PoC). The naive LLM model is simply looking for words that resemble the developer instructions and if it is found in the user input, it will unfortunately reveal the **SECRET_CODE**.

What I plan to add next is actual API calls to Anthropic, more creative payloads and incorporate some defenses to challenge the naive LLM. I plan on learning more about other OWASP LLM Top 10 Attacks by creating naive PoCs, then improving upon them with more unique payloads and layered defenses.
