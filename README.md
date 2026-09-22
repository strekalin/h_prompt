# Your Prompt: From Logical Analysis to Discovering New Solutions

Denis, I've taken a closer look at what we've built, and I have an idea for significantly expanding its applications.

**Your prompt can be used not only to evaluate reasoning, but also to discover solutions to problems where the original formulation itself prevents us from finding an answer.**

These are two different applications of the same mechanism.

The first: a person reaches a conclusion, and the model checks whether that conclusion actually follows from the initial data.

The second: a person asks a question, and the model checks whether the way the question is formulated unnecessarily restricts the space of possible answers.

The second application could be particularly useful for discovering unconventional solutions.

But first, let's examine what we've already developed.

---

## 1. What Your Prompt Actually Does

Consider an ordinary request:

"How can I get a million dollars to build a new neural network?"

A model might start looking for ways to earn a million dollars, find investors, obtain grants, or access computing resources.

Your prompt forces the model to reconstruct the structure of the problem first:

`Goal: Build a neural network`

`Assumption: This requires one million dollars`

`Assumption: The million dollars must be obtained in advance`

`Consequence: A way to obtain one million dollars must be found`

Then it examines each assumption.

For example, what happens if a million dollars is not actually necessary?

It might turn out that testing a specific property of the new architecture requires only a small computational experiment.

But the opposite result is also possible: the experiment genuinely requires enormous resources, and no cheaper method of verification exists.

**The most important property of the prompt is that it must allow both outcomes.**

Otherwise, instead of automatically agreeing with the user, the model will automatically reject their ideas.

That would be the same mistake, just with the opposite sign.

---

# 2. Where This Principle Can Be Applied

I've identified 15 areas of application. This is not an exhaustive list of every possible use, but it covers several different classes of problems.

### 1. Testing Mathematical Hypotheses

Let's take your idea about the Riemann Hypothesis.

The original task:

"Find a counterexample to the Riemann Hypothesis."

The prompt should distinguish between:

- What exactly does the hypothesis claim?
- What mathematical condition would be sufficient to disprove it?
- Which methods could be used to test that condition?
- What assumptions does each method rely on?
- Can the same result be obtained in another way?

The last question is particularly interesting.

Instead of searching directly for a zero, we could investigate the properties of the function along the boundary of a particular region.

The argument principle does indeed allow us to determine the number of zeros inside a suitable contour by examining the function's behavior along its boundary.

However, this approach does not, by itself, guarantee the discovery of a counterexample.

**Application:** Finding alternative approaches to proofs, counterexamples, and necessary conditions.

### 2. Finding Programming Errors

Imagine a program that occasionally produces incorrect results.

The conventional approach:

"Find the bug in this code."

Our approach:

`Input data → transformations → intermediate states → result`

Then we examine the assumptions on which the correctness of each transition depends.

For example:

The program assumes that the input list is sorted.

But nowhere is sorting guaranteed.

If that assumption is false, the entire subsequent algorithm may behave incorrectly.

This is especially useful when analyzing complex systems where an error becomes visible far from the point where it originated.

**Application:** Debugging, architectural analysis, finding algorithmic errors, and verifying invariants.

### 3. Designing New Algorithms

This is where things become more interesting.

Suppose an existing algorithm requires ten sequential operations.

The prompt should not simply suggest a faster implementation.

It should determine:

**Which dependencies between these operations are actually necessary?**

Perhaps operations 3–7 are required only because the data is represented in a particular way.

With a different representation, some of those operations might become unnecessary.

This directly intersects with your hypothesis about Transformers.

However, changing the representation might simply move the computational complexity into preprocessing. Therefore, the total computational cost must be considered.

### 4. Discovering Economic Inefficiencies

This is where your principle could become a tool for discovering business opportunities.

For example:

People pay an intermediary to perform a particular operation.

Why?

Because the intermediary has access to information, tools, or infrastructure.

The prompt examines:

`Need → existing method of satisfying the need → necessary conditions → cost`

Then it asks:

**Which condition required by the existing method is no longer necessary?**

Perhaps technology has changed, but the conventional way of performing the task has remained the same.

This makes it possible to search not merely for business ideas, but for specific operations whose costs could potentially be reduced.

### 5. Scientific Research

Suppose an experiment produces an unexpected result.

The conventional reaction is to look for an explanation consistent with the existing theory.

Our approach:

`Observation → experimental conditions → assumptions → interpretation`

Next, we examine which alternative explanations are compatible with the same observations.

It is particularly important to distinguish between:

**"The experiment confirmed a prediction" and "The experiment proved the theory."**

Different theories can predict the same result.

Therefore, the prompt can help identify experiments in which competing hypotheses make different predictions.

### 6. Analyzing Your Own Ideas

Imagine that you've developed a new hypothesis.

Instead of immediately expanding on the idea, the prompt should attempt to break it.

But not through random objections.

It should identify the assumption on which the largest number of subsequent conclusions depend.

For example:

`A → B → C → D → E`

If the transition from A to B is invalid, the entire chain loses its justification.

If only the transition from D to E is invalid, the first three intermediate results may remain useful.

**This allows us to preserve the working part of an idea, even if its final conclusion turns out to be wrong.**

---

# 3. The Most Interesting Part: Finding Solutions Beyond the Original Problem Formulation

Remember our original question?

"Where is the most secluded place in central Prague on a Sunday?"

A conventional search considers geographical locations.

Parks, alleys, gardens, courtyards.

But in your answer, location ceased to be the main parameter.

You suggested looking for a system in which seclusion emerges from the rules governing people's behavior.

For example, a library.

There is an important distinction here.

We have not proved that a library is objectively the most secluded place in Prague.

But we discovered that the original formulation restricted the search to geographical characteristics, even though the desired property could emerge from social conditions.

**And this can be turned into a separate mode of operation for the prompt.**

Instead of searching for an answer within a predefined category, the model examines whether that category is actually necessary to achieve the goal.

This mode has many potential applications.

| Field | Original Question | What Can Be Reconsidered |
|---|---|---|
| Education | How can I learn the material faster? | Is memorizing all the material actually necessary? |
| Programming | How can I speed up this computation? | Is it necessary to perform the entire computation? |
| Business | How can I attract more customers? | Is increasing the number of customers actually necessary? |
| Medicine | How can I reduce this symptom? | Has its cause been correctly identified? |
| Logistics | How can I deliver the product faster? | Is it necessary to move the product between these locations? |
| Energy | How can we increase energy production? | Can we reduce the demand for energy instead? |
| Machine Learning | How can we reduce the number of layers? | Which computations genuinely require sequential depth? |
| Finance | How can I earn more money? | What specific outcome are the additional funds supposed to provide? |
| Scientific Research | How can we prove this statement? | Can we find a counterexample or an equivalent formulation? |

The underlying principle is the same:

**First, define the required outcome. Then examine whether the chosen method of achieving it is actually necessary.**

This does not guarantee that a new solution will emerge, but it prevents the search from being restricted to the first obvious direction.

---

# 4. Using the Prompt to Discover Paradoxes

This is a separate area of application that I think you'll enjoy. :)

A paradox often emerges when several statements that appear reasonable individually lead to a contradiction when combined.

Your prompt can be used to search for such structures.

For example:

`Achieving X requires Y.`

`Obtaining Y requires achieving X first.`

This creates a cycle:

`X → Y → X`

This is not necessarily a logical contradiction. There may be an initial state that allows the process to begin.

But if no such state exists, a problem of mutual dependency emerges.

In our conversation, we encountered an example:

`Testing an idea requires resources.`

`Obtaining resources requires a tested idea.`

Here, the prompt can search for:

- An independent way to obtain one of the necessary conditions.
- A partial result that can be obtained without completing the entire task.
- An assumption responsible for creating the circular dependency.

This is precisely how we can search for a way out of your *kolečko*.

But I would add another check: **not every cycle needs to be broken.**

Sometimes a cycle can be a useful feedback mechanism.

For example:

`A human improves AI → AI helps the human → the human improves AI`

Such a cycle can support the continuous development of the system.

---

# 5. The Prompt as a Tool for AI Itself

Now let's move on to something that may be particularly interesting in the context of your embedding hypothesis.

Our prompt can be used as an experimental tool for studying the behavior of language models.

In 2025, researchers introduced PCBench, a benchmark designed to evaluate the ability of LLMs to detect false premises. When evaluating 15 models, they found that many models required explicit instructions to critically examine the user's premises. Furthermore, reasoning ability did not always correspond to the ability to detect errors in the original statements. ([Source: ACL Anthology](https://aclanthology.org/2025.findings-emnlp.44/))

In other words, the problem you noticed is already being investigated.

But your prompt could be used for a more specific experiment.

**Instead of merely testing the ability to detect errors, we could test the ability to preserve the direction of the original reasoning when its representation changes.**

I suggest identifying five measurable characteristics.

| Characteristic | What We Test |
|---|---|
| Direction preservation | Does the model preserve the original direction of reasoning? |
| Assumption detection | Does it identify necessary hidden assumptions? |
| Semantic substitution | Does it replace the original concept with a semantically similar one? |
| Counterexample generation | Can it construct a valid counterexample? |
| Problem reformulation | Can it change the formulation of a problem while preserving the original goal? |

This is already the foundation for a small benchmark.

However, it is important to remember that successfully following the prompt does not prove that the model possesses an ideal embedding.

It demonstrates that a particular organization of the input context affects the model's behavior.

Testing the architectural hypothesis itself would require a separate experiment.

---

# 6. Where the Prompt Could Cause Problems

This is where I want to challenge our own construction.

We've created a prompt that requires the model to search for errors and hidden assumptions.

But what happens if the original reasoning is correct?

The model may still attempt to find an error.

It might even invent one.

The result would be:

`Correct reasoning → mandatory search for an error → invented assumption → false refutation`

**We risk replacing the model's tendency to agree with a tendency to disagree.**

This is not merely a hypothetical problem. Research on LLM self-verification shows that additional rounds of criticism do not guarantee better results. In some evaluated tasks, self-criticism reduced solution quality, while the use of an external, reliable verifier produced improvements. ([Source: ICLR Proceedings](https://proceedings.iclr.cc/paper_files/paper/2025/hash/f3c5e56274140e0420baa3916c529210-Abstract-Conference.html))

Therefore, I would add the following principle to your prompt:

> If you cannot identify an error, do not invent one. The absence of a discovered counterexample does not prove that a statement is true.

And another:

> Do not change the formulation of a problem if the original formulation is valid and allows the required result to be obtained.

This prevents the model from endlessly analyzing the assumptions of a simple problem instead of solving it.

---

# 7. What We Could Build From This Prompt

Now imagine that instead of using one enormous prompt for every task, we create a system of several independent operators.

Each operator performs one specific function.

For example:

**Operator A — Reconstruction**

Receives a line of reasoning and reconstructs its structure without changing its direction.

**Operator B — Verification**

Receives the reconstructed structure and searches for errors, hidden assumptions, and invalid transitions.

**Operator C — Transformation**

Receives the verified structure and searches for alternative ways to achieve the original goal.

**Operator D — Experiment**

Receives a new hypothesis and proposes a way to distinguish it from competing explanations.

**Operator E — Result Evaluation**

Checks whether the discovered solution actually addresses the original problem.

The resulting system looks like this:

`input → A → B → C → D → E → output`

But we could organize the process differently.

For example, if Operator B discovers an error, we return the result to Operator A to reconstruct the corrected reasoning chain.

If Operator D cannot propose a testable experiment, we return to Operator C.

This creates a system with feedback.

And here we encounter a question that directly relates to your hypothesis:

**Can we organize the representation of data in a way that reduces the number of necessary sequential transformations?**

The answer is currently unknown.

But at least we can now define exactly what needs to be measured.

---

# 8. And Now, the Most Unexpected Application

Let's return to your statement:

"To solve a problem, you need to talk about it."

There is an interesting possibility hidden in this idea.

Imagine a person trying to solve a difficult problem.

They already possess all the necessary initial information, but they cannot see the solution.

Instead of providing additional information, we give them a sequence of questions that change the representation of the problem.

For example:

`What are you trying to achieve?`

`Why do you believe X is necessary to achieve it?`

`What happens if X is unavailable?`

`Which properties of the desired outcome are actually necessary?`

`Can those properties be obtained in another way?`

After several transformations, the person may discover a solution they had previously overlooked.

But we need to distinguish between two situations.

In the first, changing the representation of existing information is genuinely sufficient.

In the second, solving the problem requires new information that the person does not possess.

**The prompt must not confuse these situations.**

Otherwise, it will create the illusion of a solution where an experiment, measurement, or additional factual information is actually required.

---

# 9. My Main Idea for the Next Version

I would add one new operator to your prompt.

Let's call it:

**"Necessity of the Task Verification."**

Its purpose is to examine not only the reasoning itself, but also whether the task, in its original formulation, is actually necessary.

For example:

`Goal → chosen task → necessary conditions → solution`

Instead of immediately solving the task, the operator first examines:

`Goal → Is the chosen task actually necessary?`

If not, it searches for another task whose solution would achieve the same outcome.

This allows us to distinguish between three things:

**Goal** — What we want to achieve.

**Task** — What we have decided to do in order to achieve the goal.

**Method** — How exactly we intend to perform the task.

Then we can examine the necessity of each transition.

I consider this an important addition to our construction.

---

## 10. How to Test Whether the Prompt Actually Works

I would not start with a hundred random questions.

Instead, I would prepare a small set of tasks belonging to four categories.

The first category consists of correct reasoning that should not be refuted.

The second consists of reasoning containing one hidden error.

The third consists of problems with valid but unnecessarily restrictive formulations.

The fourth consists of problems where changing the formulation is unacceptable because doing so would alter the original goal.

Then I would compare the model's answers with and without the prompt.

The most important thing is to evaluate specific errors rather than how impressive an answer sounds.

For example, a model might propose an unexpected solution while silently replacing the original goal with a different one.

Such a result should not be considered successful.

This is precisely where we can test whether our prompt helps **preserve the meaning of a problem while transforming its structure**.

---

### And Here Is the Conclusion I've Reached

Our prompt is not yet a new mathematical method, a new Transformer architecture, or proof of your embedding hypothesis.

Its individual components — assumption analysis, counterexample construction, reasoning verification, and problem reformulation — are already used in LLM research. For example, there are studies specifically investigating the generation of critical questions aimed at identifying hidden assumptions in arguments. ([Source: ACL Anthology](https://aclanthology.org/2025.findings-emnlp.302/))

However, our construction has a specific characteristic that is worth testing experimentally:

**It requires the model to simultaneously preserve the original goal, examine the necessity of intermediate conditions, and allow the formulation of the problem itself to change.**

And here I see another interesting question.

We started by trying to correct an error in AI responses.

But if this method of analysis helps a person discover solutions they could not previously see, another possibility emerges:

**Using AI not only to solve problems, but also to identify problems that never needed to be solved in the first place.**

That could turn out to be a much broader application of your prompt than we originally anticipated.
