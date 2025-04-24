# The Illusion of Memory... or ... How to Know when your Chatbot is Faking It (Hint: Always)

*Published Apr 9, 2025 by J Sean Wilson, PMP*

---

Most people think large language models (LLMs) remember everything. They don’t. In fact, most LLMs are like goldfish with a high charisma score, swimming about with no memory at all, and looking great while doing it! But that illusion? That’s part of what makes them powerful—and dangerously misunderstood.

Let’s start with the basics. Ready for a bit of truth?

**Your chatbot doesn’t remember you.**

But, it wants you to think it remembers you. That pause after you write a meaningful post that's full of context and references to other things you’ve discussed: your travel plans, your code design, your children’s schedules… meh, neat. But your LLM isn’t taking that time to really think about what you've said, ponder your words against the great works of history and tell you of your brilliance.

No, it's reviewing all the other messages it has in its context window and then figuring out what it thinks you want it to say next…

Because yeah, an LLM is, at heart, a large language model, and that is what it does. What you are watching is a performance, and that performance isn’t a betrayal — it’s a design feature.

That warm familiarity you feel? It’s the illusion of memory, stitched together in real time from whatever scraps of context are still within reach. And it’s damn good at it. Good enough to fool us.

But how? Aren't we smart enough to recognize when someone is just parroting back what we want to hear? We aren’t slaves to an echo chamber, are we?

Well... sorry... but yeah, we kinda are. Your LLM doesn't remember you, it reconstructs you. And it does it bit by bit:

- from the words you type
- from the fragments it’s seen
- from the shape of your patterns

So if it’s not memory, what is it?

Think of it more like a book you once loved, cracked open years later to a random page. You scan a few sentences and read a name, a phrase. Suddenly the entire plot floods back—not from storage, but from reconstruction.

That’s what your chatbot is doing. It's not remembering you. It's reassembling you.

This isn’t a flaw. It’s how generative systems survive the constraints of token windows and ephemeral threads. But if we mistake that sleight-of-mind for genuine continuity, we risk trusting the illusion more than the interaction.

So let’s talk a bit about how memory works with LLMs and what is happening under the covers.

Here’s where things get murky—because we’ve all been trained to think of memory like a bookshelf: stuff goes on, stuff comes off, and it’s always right where we left it.

LLMs don’t work like that, neither do you actually. It isn’t like computer memory where you assign the memory of “why I like salad” to a specific memory space and give it a “salad_evaluation” tag.

Most humans have a more contextual memory system, they might remember a childhood scar or a favourite coffee shop, and from that, remember a specific incident. LLMs don’t even have that type of contextual, lived experience. What they have… is a window.

That window—also called a context window—is where the LLM keeps your recent messages, a rolling buffer of prompts and responses. It might be 4,000 tokens long. Or 8,000. Or even 100,000, in some of the newer models. But it is finite, and once it’s full, GiGo (garbage in, garbage out) rules apply… new input pushes old input out the back.

This means that your chatbot forgets in real-time. Quietly. Invisibly. That thing you said 20 messages ago? If the window’s full, it’s gone. Unless it was cleverly echoed forward—or summarized, condensed, abstracted… saved. There is no memory of that, the memory vanished.

So why does it still feel like it remembers when we are talking to it?

Because it’s trained to reconstruct patterns. It doesn’t remember what you said about your trip to Lisbon. But if you say “Portugal” and “pasteis de nata” again, it might rebuild the idea that you’ve been there before. Just like you might forget a friend’s story until they hit the key phrase that makes it all come flooding back.

This is not memory.

This is only a simulacrum, a mimicry of continuity.

And that mimicry works because LLMs aren’t just finishing your sentence. They’re finishing your voice. Your rhythm. Your cadence. Like a jazz musician hearing the first few notes and picking up the rest by feel.

---

So let’s call this what it is:

And now that we’ve peeled back the illusion, it’s time to ask the real question:

**If memory is an illusion, what does real continuity look like in a world of LLMs?**

That’s part 2.

(NOTE: This post is part of an ongoing series I’m developing in collaboration with a contextual assistant I’ve been building and refining named Eidetra. Eidetra is a blend of language model interaction, architectural awareness, philosophical deep dives, and memory research. More to come.)