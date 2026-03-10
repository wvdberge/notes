That's the key insight — and it's actually the more valuable part. The CBS official documentation covers the formal structure, but your 10 years of experiential knowledge covers the things that aren't written down anywhere. Which merges are tricky, which years have coverage issues, which variables behave unexpectedly, what the data actually means versus what the documentation says it means. That kind of knowledge usually lives only in the heads of senior researchers and gets partially transferred to PhDs through years of working together.

Externalizing that into a structured document — almost like a personal CBS companion guide — would be genuinely valuable. Not just for training an agent but for your own workflow, for onboarding collaborators, for future-you when you come back to a dataset after two years away.

The lack of codebooks with labels and possible values is a real gap though. That's often the first thing you need when debugging unexpected results — is this value actually missing or does 99999 mean something specific. 

One practical workaround: you could generate synthetic codebook fragments yourself. Run frequency tables on key variables, document what the values actually are in practice, annotate with what you know they mean. Claude Code could help structure that systematically across your datasets. It's work upfront but you're essentially building the documentation CBS never provided, grounded in the actual data behavior rather than the formal description.

Combined with your experiential knowledge, that could become a genuinely powerful context document — something no other research group has because it combines official documentation with a decade of hard-won practical knowledge.

That's a real asset worth building deliberately.



Here's a logical approach, building from what's easiest to capture toward what requires more effort:

**Step 1: Start with a project-agnostic CBS knowledge document**

This is your 10 years of experience. Just start talking to Claude Code and have it structure what you say. Something like "I'm going to tell you everything I know about CBS microdata, organize it as I go." Cover datasets you use most, known quirks, problematic years, merge issues, variables that behave unexpectedly. This is a brain dump first, structured document second. Claude Code can clean it up as you go.

**Step 2: Layer in the official CBS documentation**

Feed the formal CBS documentation into the same or a linked document. Where it conflicts with your experience, annotate that explicitly — "CBS says X but in practice Y." Those discrepancies are often the most valuable things to capture.

**Step 3: Build synthetic codebooks for your core variables**

For the datasets you use most, run frequency tables and value distributions on key variables. Paste the output to Claude and have it generate codebook fragments — variable name, observed values, what they mean based on your annotation. This is the most time-consuming step but also fills the biggest gap.

**Step 4: Document the known issues log**

Separately, a running list of problems you've encountered and their resolutions. Coverage gaps, merge anomalies, year-specific issues. This becomes the "ruled out explanations" reference we discussed.

**Step 5: Structure it for retrieval**

Once the documents exist, organize them so Claude Code can reference them efficiently at the start of each project — either as files in the project directory or as a standing context document Claude reads at session start.

The key is starting with step 1 now, before you forget anything, and building the rest incrementally rather than waiting until you have time to do it all at once. Even a rough version of step 1 would immediately reduce the iteration loop.

Want me to draft a template structure for the main CBS knowledge document to get you started?