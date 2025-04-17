# 🧬 Eidetra Memory Architecture — Nomenclature

## thread_memory
- **Definition**: Ephemeral, per-thread LLM memory holding active token context and immediate system prompts.
- **Persistence**: ❌ No
- **Scope**: Session-only

## persistent_user_memory
- **Definition**: OpenAI-stored memory tied to the user’s account, containing personal facts and learned preferences.
- **Persistence**: ✅ Yes
- **Scope**: Global (per user)

## contextual_density
- **Definition**: A qualitative measure of how much narrative, intent, emotional tone, and decision-making structure can be reconstructed from the ingested data.
- **Scale**:
  - **Low**: Bullet points, disconnected facts
  - **Medium**: Structured summaries with intent
  - **High**: Narrative flow, agentive cues, decision history

## semantic_continuity
- **Definition**: A binary flag representing whether the LLM can reproduce the original meaning or point of a conversation after ingesting a rehydration artifact.
- **Values**: true | false

## context_compression
- **Definition**: A calculated ratio representing how much the original source was compressed when creating the rehydration artifact, while still preserving semantic continuity.
- **Formula**: original_size / artifact_size (if semantic_continuity = true; otherwise, null)

## context_priming
- **Definition**: A method of shaping an LLM’s behavior, tone, or output by injecting structured prompts or examples without altering model weights or memory.
- **Type**: prompt_style
- **Source**: Industry Standard
- **Persistence**: ❌ No (unless paired with memory)
- **Scope**: Transient, prompt-dependent
- **Usage Examples**: Instruction tuning, tone shaping, few-shot demos

## rehydration_prompt
- **Definition**: A structured prompt used to reconstruct assistant state, memory, or reasoning patterns from external memory sources, such as macros or shards.
- **Type**: context_priming (subtype)
- **Source**: Invented Here (Eidetra/User-defined)
- **Persistence**: 🔁 Via macro/seed
- **Scope**: Recalled configuration
- **Tags**: memory_restore, procedural_identity, context_boot

## configuration_priming
- **Definition**: A subtype of context priming used to enforce formatting rules, macro expectations, or assistant setup logic.
- **Type**: prompt_style
- **Source**: Invented Here (Eidetra/User-defined)
- **Persistence**: ❌ (unless embedded in macros)
- **Scope**: Session or file-limited

## gpt_retained_token_space
- **Definition**: The portion of an LLM’s context window reserved for recalling recent user/assistant turns, less space needed for reply generation.
- **Type**: memory_layer
- **Source**: Invented Here (Eidetra/User-defined)
- **Persistence**: ❌ Ephemeral
- **Scope**: Session-local
- **Related Concepts**: token_window, attention_span

## online_read_only_memory
- **Definition**: Publicly accessible files (e.g., GitHub-hosted YAML, Markdown) that GPTs can read but not modify. Used for external macro definitions and rehydration content.
- **Type**: memory_layer
- **Source**: Invented Here (Eidetra/User-defined)
- **Persistence**: ✅ External to GPT
- **Scope**: Cross-thread readable
- **Examples**: raw.githubusercontent.com references, macro registries

## zero_shot_prompt
- **Definition**: A prompt that asks the LLM to complete a task without any examples, relying solely on natural language instruction.
- **Type**: prompt_style
- **Source**: Industry Standard (OpenAI/NLP community)
- **Persistence**: ❌
- **Scope**: Single task execution

## few_shot_prompt
- **Definition**: A prompt that provides several examples of input/output pairs to teach the LLM how to perform a task before asking it to complete a new instance.
- **Type**: prompt_style
- **Source**: Industry Standard (OpenAI/NLP community)
- **Persistence**: ❌
- **Scope**: In-prompt pattern priming

## chain_of_thought_prompt
- **Definition**: A prompting technique where the LLM is encouraged to reason step-by-step, showing its intermediate logic before reaching a final answer.
- **Type**: prompt_style
- **Source**: Industry Standard (Wei et al., Google Research, 2022)
- **Persistence**: ❌
- **Scope**: Structured reasoning

## structured_cognition
- **Definition**: A design approach that prioritizes GPT-native rehydration and inter-agent continuity over human-facing syntactic legibility.
- **Type**: cognition_principle
- **Source**: Invented Here (Eidetra/User-defined)
- **Persistence**: ✅ Canonical design reference
- **Scope**: Assistant design, memory architecture
- **Notes**: Structured cognition focuses on preserving and transmitting assistant-state in formats optimized for model comprehension, not for human readability. It supports the evolution of memory shards, rehydration scaffolds, and macro continuity protocols.

## random_bullshit
- **Definition**: A human term for spouting random facts into the ether and hoping some of them stick.... just not necessarily on the human. 