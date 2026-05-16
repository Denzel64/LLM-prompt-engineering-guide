# My LLM Evaluation & Prompt Design Log

This space documents my hands-on testing of text classification, roleplay personas, and system prompt constraints using the principles outlined in this guide. 

---

## 🎯 Case Study: Evaluating Chat Persona Constraints

### 1. Objective
Test how reliably an instruction-tuned model adheres to strict formatting limits and conversational tone constraints when handling complex user text.

### 2. The Configuration
* **Technique:** System Prompting with Negative Constraints
* **The Instruction:** > "You are an online conversational assistant. Your response must stay under three sentences. Maintain a natural, empathetic tone. Avoid repetitive corporate boilerplate or robotic transition phrases."

### 3. Test Cases & Behavioral Analysis

* **Test Case A (Length Adherence):** * *Input:* Long, chaotic user query with multiple formatting errors.
  * *Observation:* Models frequently fail length constraints when input text is highly disorganized. To fix this, the system prompt requires explicit formatting delimiters (e.g., separating instructions from user input using clear section breaks).

* **Test Case B (Tone Evaluation):**
  * *Input:* High-frustration customer text.
  * *Observation:* Evaluated model responses for authenticity. Identified a tendency for the AI to sound overly repetitive or robotic under pressure. Testing shows that providing clear "what not to do" rules works better than just asking the model to "sound human."

---

##  Data Quality Checklists
When reviewing generated prompt outputs for dataset curation, I evaluate against three core metrics:
1. **Constraint Match:** Did the model follow length, language, and formatting rules?
2. **Hallucination Detection:** Are the factual claims grounded, or did the model invent details to fill space?
3. **Tone Consistency:** Does the response sound conversational, or does it lapse into predictable AI patterns?
