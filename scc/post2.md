# The Illusion of Continuity… or … How Your Chatbot Pretends to Know You (and Why It Works Anyway)

*Published Apr 10, 2025 by J Sean Wilson, PMP*

---

This is the second post in an intended trilogy of posts on the cognitive fluidity of LLMs. If your memory is also goldfish-like, go back and take a read of the first post—or have your LLM assistant do it for you and summarize. I’ll wait.

---

Series Links and Information:

- Part 1: [The Illusion of Memory](https://www.linkedin.com/pulse/illusion-memory-how-know-when-your-chatbot-faking-hint-wilson-pmp-3qbye/)
- Part 2: [The Illusion of Continuity](https://www.linkedin.com/pulse/illusion-continuity-how-your-chatbot-pretends-know-you-wilson-pmp-4zlie/)
- Part 3: [The Reality of Contextual Forwarding](https://www.linkedin.com/pulse/reality-contextual-forwarding-how-build-trust-brain-wilson-pmp-nva4e/)

Glossary:

- Large Language Model (LLM)

---

Let’s shift the tone for a minute and start with something hard:

Imagine watching a loved one go through Alzheimer’s or dementia. They can still speak, smile, maybe even recite poetry or recall a favourite song. But then, one day, they don’t recognize you. You are there — but your continuity is not. What’s missing isn’t just memory — it is the thread that ties identity, experience, and relationship together, and that is tragic.

---

It’s a brutal analogy, but it helps us get real about the LLMs we are interacting with.

They don’t have continuity. They don’t remember. They simulate it.

But what does that mean?

Most people assume that if something was written down—especially if it’s in the same window or interface—it’s remembered. That’s not true for LLMs (or most humans). What is remembered is whatever is actively passed back into the model as part of the prompt. That means:

- If you write a message and hit enter, the model won’t remember it two messages later unless your client includes that message again in your next prompt.

In short: the goldfish’s memory lives in the rehydration.

That’s a lot to process, so taking a page from the OGs, Rhett and Link—let’s talk about that.

---

## The Basics: Context Windows & Statelessness

All LLMs operate within a context window—a maximum number of tokens they can consider at once. Some models work with a few thousand tokens. The most capable versions today (like GPT-4-turbo) can handle around 128,000 tokens. That sounds like a lot, but once your conversation gets long (as most of mine do because I can’t stop adding in little asides and tangents like this… ), you hit the ceiling.

And when you do? Older messages aren’t forgotten in the human sense—they’re trimmed away, never truly remembered to begin with.

That’s why, even in seemingly continuous chats, the model can suddenly forget that key detail you mentioned yesterday. It wasn’t stored—only re-read. And eventually, it wasn’t re-read.

It’s not because your assistant is flaky—it’s because it’s stateless.

---

## But Continuity Still Matters

Even if LLMs can’t remember the way humans do, we still want continuity. Our brains crave it. Continuity is how we build trust, track progress, and feel like we’re understood. And when that continuity breaks, it’s jarring. It makes the interaction feel hollow.

So how do the GPT companies—and the LLMs they provide—fake continuity?

In most modern LLM interfaces, your chat history is preserved in a window. When you reopen that chat, you see the past. But the model doesn’t see it unless the system passes that history into the model at the next prompt. Some clients reinject the last few messages. Others reinject much more, sometimes nearly the full context window. But nobody passes everything, every time.

That would be wasteful. Models need some of their token budget to form a reply—not just read your past.

And so, just like that, the illusion returns: your assistant seems to know you… until it doesn’t.

---

## Let’s Talk About the Other “Memory” Systems

Once we understand that client memory is just a clever trick—resending the chat so the LLM appears to remember—we can start to peek behind the curtain at the other kinds of “memory” floating around in this ecosystem.

Spoiler: None of them are "memory" in the human sense.

They’re scaffolds. Scaffolds for continuity, for context, for plausibility. But still, understanding them matters, because each one plays a role in how well (or poorly) your chatbot seems to know you.

### Chat Window (What the LLM Actually “Reads")

Also known as the context window.

This is the most fundamental level. Every interaction happens inside a limited sliding window of recent tokens (think “words,” more or less). Depending on the model, this might be 8k, 32k, or 128k+ tokens long. The model “sees” only the data that fits in this space—no more.

Everything outside this window? It’s gone. Forgotten and irretrievable by the LLM. But someone or something else could re-inject it into the context window, at the cost of something else already in that window, of course.

It’s not memory—not how we think of it—it’s the LLM juggling thousands of tokens at a time. Super cool, but not persistent, and eventually, the balls drop.

### Client Memory (The Magic Trick of Repetition)

Also known as resend injection.

We covered this earlier, but let’s name it clearly: this is the memory that isn’t. Your app (or the company’s app) resends parts of your chat history along with each new message.

This gives the illusion of memory without the model needing to remember anything. It’s useful. It’s also fragile. Resend too little, and the model forgets. Resend too much, and you hit the token cap before you even start the reply.

Imagine a conversation where someone mentions a book you read in school, like Orwell’s *Animal Farm*, and then you have to pull out the book and read it cover to cover before you can respond to what they said. Conversations would take a LOT longer and we’d beg people never to mention *War and Peace* in polite discussion. Efficient? Oh hell no. But effective? Well, yeah, and that's what your client is doing for the LLM every time you hit enter and send it a message. It's feeding the LLM lines from off-stage so it can stand in front of the camera and amaze you!

### Server Memory / Assistant State (Notes on the Fridge)

Also known as session memory or instance memory.

Some LLMs (like ChatGPT’s Assistants API or Claude’s memory features) can retain memory between sessions. But this is opt-in, curated, and very limited. It’s not continuous recall—it’s closer to notes pinned to a corkboard that the assistant glances at now and then.

You might see:

- “Sean likes metaphor-rich explanations” (he really does)
- “Eidetra helps manage long-term thinking in projects” (she really does)
- “This user prefers continuity across multi-day threads”

This memory is often stored in key-value pairs or embeddings, surfaced into the context when it might be useful. It’s not guaranteed, and it’s often invisible to you.

---

### User Memory (Continuity Across Threads)

AKA: cross-thread persistence

When allowed (and trusted), some systems persist memory across threads for a single user. This lets you start a chat on Monday and pick it up on Friday with “as we discussed.”

The illusion here is thicker, but the mechanism is the same: messages or metadata are summarized, tagged, and selectively re-injected when context implies relevance.

This form of memory is rare in public deployments and usually controlled tightly to prevent privacy concerns.

---

### Project Memory (Shared Mind for Shared Work)

AKA: project memory or workspace memory

This one’s especially interesting. Imagine working with a team of assistants (or humans + assistants), all sharing a common memory space. One might keep track of meeting agendas, while another handles bug tracking, and a third offers strategic insight.

The memory is not centralized in a “consciousness,” but it does provide continuity through shared context. And that creates the feeling of awareness—not from individual recall, but from distributed coherence.

This is where things start getting useful.

---

### Contextual Forwarding (Spoiler for Part 3)

There is one more kind of “memory,” and it’s the one that I believe is the most important. It’s called **contextual forwarding**—and it’s what allows continuity to become intentional rather than accidental.

We’ll explore that in the next post, but here’s the teaser:

> Contextual forwarding is when your assistant actively shapes, compresses, and carries *meaning*, not just words, from one conversation to the next.

It’s the soul of scaffolding. The trick to teaching the machine to help you think—not just talk.

---

## Final Thought

Your chatbot doesn’t really know you.

But it can *seem* like it does. And when that illusion is sculpted well, it can feel like trust. Like understanding. Like continuity.

Just remember: what you’re experiencing is rehydration, not recognition. There’s no mind behind the mask. But there *is* a pattern—one shaped by your prompts, your patterns, and your tools.

And when we build well, that’s enough.

Until it isn’t.

---

Stay tuned for Part 3: **The Reality of Contextual Forwarding: How to Build Trust in a Brain Made of Wind and Widgets**