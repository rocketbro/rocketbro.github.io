---
layout: post
title: "Loom: LLMs Are Multiverse Generators"
date: 2024-11-16
tags: []
---

*Note: I did not write this. This is an article version of a seminal paper to the theory behind [Loom: LLM Interface](https://rocketbro.github.io/projects/loom), and I thought it made sense to post an easy-to-read version here on the blog. [Read the original paper here.](https://arxiv.org/abs/2102.06391)*

{% include image.html 
   file="multiverse01.png" 
   alt="the multiverse" 
   height="150"
%}

# Multiversal views on language models

Laria Reynolds  
moire@knc.ai

Kyle McDonell  
kyle@knc.ai

## Abstract

The virtuosity of language models like GPT-3 opens a new world of possibility for human-AI collaboration in writing. In this paper, we present a framework in which generative language models are conceptualized as multiverse generators. This framework also applies to human imagination and is core to how we read and write fiction. We call for exploration into this commonality through new forms of interfaces which allow humans to couple their imagination to AI to write, explore, and understand non-linear fiction. We discuss the early insights we have gained from actively pursuing this approach by developing and testing a novel multiversal GPT-3-assisted writing interface.

**Keywords**: writing assistant, hypertext narratives, multiverse writing, GPT-3

## 1 Introduction

GPT-3 [4], OpenAI's new generative language model, has astonished with its ability to generate coherent, varied, and often beautiful continuations to natural language passages of any style. To creative writers and those who wish themselves writers, such a system opens a new world of possibilities. Some rightfully worry whether human writing will become deprecated or worthless in a world shared with such generative models, and others are excited for a renaissance in which the creative powers of human writers are raised to unprecedented heights in collaboration with AI. In order to achieve the latter outcome, we must figure out how to engineer human-machine interfaces that allow humans to couple their imaginations to machines and feel freed rather than replaced. We will present the still-evolving approach we have learned over several months of testing and designing interfaces for writing with the aid of GPT-3, beginning by introducing the framework of language models as multiverse generators.

## 2 Language models are multiverse generators

Autoregressive language models such as GPT-3 take natural language input and output a vector of probabilities representing predictions for the next word or token. Such language models can be used to generate a passage of text by repeating the following procedure: a single token is sampled from the probability distribution and then appended to the prompt, which then serves as the next input. As the sampling method can be stochastic, running this process multiple times on the same input will yield diverging continuations. Instead of creating a single linear continuation, these continuations can be kept and each continued themselves. This yields a branching structure, which we will call a multiverse, or the "subtree" downstream of a prompt as shown in Figure 1.

[Figure 1: Diagram showing the process of generating a multiverse story with a language model. The probability distribution is sampled multiple times, and each sampled token starts a separate branch. Branching is repeated at the next token (or per set interval, or adaptively), resulting in a branching tree structure.]

[Figure 2: Image showing a narrative tree with initial prompt "In the beginning, GPT-3 created the root node of the"]

### 2.1 Analogy to Everettian quantum physics

Quantum mechanics tells us that the future is fundamentally indeterminate. We can calculate probabilities of future outcomes, but we cannot know with certainty what we will observe until we actually measure it. The problem is not merely epistemic; the future truly has not yet been written, except in probabilities. However, when we do finally venture to measure it, the ambiguous future seems to us to become a concrete, singular present.

The Everettian or many-worlds interpretation of quantum mechanics, which has become increasingly popular among quantum physicists in recent years, views the situation differently [6]. It claims that we, as observers, live in indeterminacy like the world around us. When we make a measurement, rather than collapsing the probabilistic world around us into a single present, we join it in ambiguity. "We" (in a greater sense than we normally use the word) experience all of the possible futures, each in a separate branch of a great multiverse. Other branches quickly become decoherent and evolve separately, no longer observable or able to influence our subjective slice of the multiverse.

This is the universe an autoregressive language model like GPT-3 can generate. From any given present it creates a functionally infinite multitude of possible futures, each unique and fractally branching.

David Deutsch, one of the founders of quantum computing, draws a connection between the concept of a state and its quantum evolution with virtual reality generation [5]. He imagines a theoretical machine which simulates environments and models the possible responses of all interactions between objects. Deutsch further posits that it will one day be possible to build such a universal virtual reality generator, whose repertoire includes every possible physical environment.

Language models, of course, still fall well short of this dream. But their recent, dramatic increase in coherence and fluency allow them to serve as our first approximation of such a virtual reality generator. When given a natural-language description of objects, they can propagate the multiverse of consequences that result from a vast number of possible interactions.

### 2.2 Dynamic and interpretational multiplicity

Deutsch's view emphasizes that from any given a state there are a multiplicity of possible future single-world dynamics; stories unfold differently in different rollouts of an identical initial state. There is another dimension of multiplicity that we must also consider, especially when we are talking about states defined by natural language.

Natural language descriptions invariably contain ambiguities. In the case of a narrative, we may say that the natural language description defines a certain present – but it is impossible to describe every variable that may have an effect on the future. In any scene there are implicitly many objects present which are not specified but which may conceivably play a role in some future or be entirely absent in another.

The multiverse generated by a language model downstream of a prompt will contain outcomes consistent with the ambiguous variable taking on separate values which are mutually inconsistent. So we define two levels of uncertainty, which can both be explored by a language model:

1. An uncertainty/multiplicity of present states, each associated with
2. An uncertainty/multiplicity of futures consistent with the same "underlying" present

We will call the first form of multiplicity interpretational multiplicity, and the second form dynamic multiplicity.

## 3 Human imaginations are multiverse generators

Humans exist in a constant state of epistemological uncertainty regarding what will happen in the future and even what happened in the past and the state of the present [12]. We are then, by virtue of being adapted to our uncertain environments, natural multiverse reasoners.

David Deutsch also points out that our imaginations, which seek to model the world, mimic reality as virtual reality generators: we model environments and imagine how they could play out in different branches.

### 3.1 Reading as a multiversal act

When a piece of literature is read, the underlying multiverse shapes the reader's interpretations and expectations. The structure which determines the meaning of a piece as experienced by a reader is not the linear-time story but the implicit, counterfactual past/present/future plexus surrounding each point in the text given by the reader's projective and interpretive imagination.

More concretely stated, at each moment in a story, there is uncertainty about how dynamics will play out (will the hero think of a way out of their dilemma?) as well as uncertainty about the hidden state of the present (is the mysterious mentor good or evil?). Each world in the superposition not only exerts an independent effect on the reader's imagination but interacts with counterfactuals (the hero is aware of the uncertainty of their mentor's moral alignment, and this influences their actions). The reader simulates the minds of the characters and experiences the multiverses evoked by the story.

### 3.2 Writing as a multiversal act

A writer may have a predetermined interpretation and future in mind or may write as a means of exploring the interpretative and/or dynamic multiverse. Regardless, a writer must be aware of the multiplicity which defines the readers' and characters' subjective experiences as the shaper of the meaning and dynamics of the work. The writer thus seeks to simulate and manipulate that multiplicity.

We propose that generative language models in their multiversal modality can serve as an augmentation to and be augmented by the writer's inherently multiversal imagination.

### 3.3 Writing multiverses

So far we've implicitly assumed that, despite the multiversal forces at work, the writer's objective is to eventually compose a single history. However, language models naturally encourage writing explicitly multiversal works.

In the same way that hypertext transcended the limitations the linear order in which physical books are read, exciting a surge of multiversal fiction [2], language models introduce new possibilities for writing nonlinear narratives.

After all, it's only a small leap from incorporating multiverses in the brainstorming process to including them in the narrative. Counterfactual branches often occur in traditional fiction in the form of imaginary constructs, and our minds are naturally drawn to their infinite possibility [1].

## 4 Interfaces

We propose the creation of new tools to allow writers to work alongside language models to explore and be inspired by the multiverses already hiding in their writing.

Research into hypertext writing tools has been ongoing for more than two decades and has produced notable tools like StorySpace[3]. However, the issue of hypertext interfaces assisted by language models is a newer development, as only very recently have language models become advanced enough to be useful in the writing process [9]. Likewise, there has been significant research into interactive narratives, including in branching, multiversal settings [10, 11], but never one in which the human and the language assistant can act together as such high-bandwidth partners.

As has been shown in past hypertext interface design studies [8], the primary concern in the creation of an interface for writing multiverse story is the massive amount of information that could be shown to the writer. If intuitive user experience is not central to the design of the program, this information will feel overwhelming and functionally prevent the user from leveraging the power offered by multiverse access at all.

An effective multiversal interface should allow the writer, with the aid of a generative language model, to expose, explore, and exploit the interpretational and dynamic multiplicity of a passage. Not only will such a tool allow the user to explore the ways in which a scenario might play out, such an interface will also expose previously unnoticed ambiguities in the text (and their consequences).

Depending on the design of the interface and the way the user approaches it, many different human-AI collaborative workflows are possible. Ideally, the interface should give the user a sense of creative superpowers, providing endless inspiration combined with executive control over the narrative, as well as allowing and encouraging the user to intervene to any degree.

### 4.1 Progress so far

Over the past several months, we have prototyped and tested several iterations of multiversal writing tools using GPT-3 as the generation function.

The demand for a multiversal writing application grew from use of GPT-3 as a more standard linear writing assistant. It became increasingly clear, as users sought greater interaction bandwidth and more efficient ways to structure and leverage the model's ideas, that an interface which organizes the model's outputs in a branching tree would be more effective.

The early results we have seen leave no doubt about the power of language models as writing assistants. Our small cohort of five beta users have, alongside GPT-3, co-written linear and nonlinear stories spanning the equivalent of thousands of pages of often astonishing ingenuity and beauty and surprisingly long-range coherence. Three users have reported a sense of previously unimagined creative freedom and expressive power.

However, it has also become evident that much more research and development is necessary. In our beta-tests, we've found that flaws in interface design can easily overwhelm or damage a feeling of ownership over the work produced. Below we will share some of our findings, which represent only the first step in creating a true interface between the creative mind and the machine.

### 4.2 Multiple visualizations

We have found that a visual representation of the branching structure of the narrative helps users conceptualize and navigate fractal narratives. This view (called visualize) displays the flow of pasts and futures surrounding each node (Figure 3) and zooming out displays the global structure of the multiverse (Figure 4). The visualize view allows users to expand and collapse nodes and subtrees, as well as "hoist" any node so that it acts as the root of the tree. Altering the topology of the tree, (e.g. reassigning children to different parents, splitting and merging nodes) is more intuitive for users in the visualize view than the linear view.

[Figure 3: Screenshot of the Visualize view interface]

[Figure 4: Screenshot showing a zoomed-out visualization of a nonlinear story]

In addition to tree-based multiverse visualization, the read view displays the text of a node and its ancestry in a single-history format (Figure 5).

[Figure 5: Screenshot of the Read view interface]

### 4.3 Multiverse navigation

With a generative language model, story multiverses can quickly become too large to navigate through node connections alone. To assist navigation, we have implemented the following features:

* Search all text or text in a subtree and/or text in a node's ancestry
* Indexing by chapters: Chapters are assigned to individual nodes, and all nodes belong to the chapter of the closest ancestor that is the root of a chapter. As a consequence, chapters have the shape of subtrees.
* Bookmarks and tags: Bookmarks create a named pointer to a node without enforcing chapter membership. Tags are similar to bookmarks, but can be applied to multiple nodes.

### 4.4 Adaptive branching

A naive way to automatically generate a multiverse using a language model might involve branching every fixed n tokens. However, this is not the most meaningful way to branch in a story. In some situations, there is essentially one correct answer for what a language model should output next. In such a case, the language model will assign a very high confidence (often >99%) for the top token. Branching at this point would introduce incoherent continuations. Conversely, when the language model distributes transition probabilities over multiple tokens, branching is more likely to uncover a rich diversity of coherent continuations.

One algorithm to dynamically branch is to sample distinct tokens until a cumulative probability threshold is met. Adaptive branching allows visualization of the dynamics of the multiverse: stretches of relative determinism alternating with divergent junctures (Figure 6).

[Figure 6: Screenshot showing a subtree generated with adaptive branching]

### 4.5 Reciprocal workflow

Humans retain an advantage over current language models in our ability to edit writing and perform topological modifications on the multiverse such as merging interesting aspects of two separate branches into one.

The interface should ideally allow the human to perform all desired operations with maximal ease. Because GPT-3 is so capable of producing high-quality text, some interface designs make it feasible for the human to cultivate coherent and interesting passages through curation alone. We have found that an interface which makes it easy to generate continuations but relatively difficult to modify the content and topology of the resulting multiverse encourages a passive workflow, where the user relies almost exclusively on the language model's outputs and the branching topology determined by the process of generation.

While such a passive mode can be fun, resembling an open-ended text adventure game, and as well as useful for efficiently exploring counterfactuals, the goal of a writing interface is to facilitate two-way interaction: the outputs of the language model should augment and inspire the user's imagination and vice versa.

Thus, we are are developing features to encourage meaningful and unrestrained human contribution such as:

* Easy ways to edit, move text, and change tree topology
* Support for nonstandard topologies that are not automatically generated by language models and require human arrangement, such as cycles and multiple parents (§4.7)
* Floating notes to allow saving passages and ideas independent from the tree structure (§4.6)
* Fine-grained control over language model memory (§4.8)
* Interactive writing tools that offer influence over the narrative in ways other than direct intervention (§4.9)
* Program modes which encourage manual synthesis of content from multiverse exploration into a single history, for instance by distinguishing between exploratory and canonical branches

### 4.6 Floating notes

Floating notes are text files which, rather than being associated with a particular node, are accessible either globally or anywhere in a subtree. We decided to implement this feature because users would often have a separate text file open in order to copy and paste interesting outputs and keep notes without being constrained by the tree structure. Floating notes make it easier for the user exert greater agency over the narrative.

### 4.7 Nonstandard topologies

The interface supports nodes with multiple parents and allows cyclic graphs (Figure 7). Opportunities to arrange convergent and cyclic topologies, which do not occur if the language model is used passively, encourage human cowriters to play a more active role, for instance, in arranging for separate branches to converge to a single outcome. Multiversal stories naturally invite plots about time travel and weaving timelines, and we have found this feature to unlock many creative possibilities.

[Figure 7: Screenshot showing nodes with multiple parents, allowing for cyclic story components]

### 4.8 Memory management

GPT-3 has a limited context window, which might seem to imply limited usefulness for composing longform works like novels, but our users have found that long-range coherence is surprisingly easy to maintain. Often, the broad unseen past events of the narrative are contained in the interpretational multiplicity of the present and thus exposed through generations, and consistent narratives are easily achieved through curation. In order to reference past information more specifically, often all that is needed is minimal external suggestion, introduced either by the author-curator or by a built-in memory system. We are developing such a memory system which automatically saves and indexes story information from which memory can be keyed based on narrative content.

### 4.9 Writing tools

Beyond direct continuations of the body of the story, a language model controlled by engineered prompts can contribute in an open-ended range of modalities. Sudowrite[7] has pioneered using GPT-3 powered functions that, for instance, generate sensory descriptions of a given object, or prompt for a twist ending given a story summary.

The ability to generate high-quality summaries has great utility for memory and as input to helper prompts and forms an exciting direction for our future research. We are exploring summarization pipelines for GPT-3 that incorporate contextual information and examples of successful summarizations of similar content.

## 5 Conclusion

The problem of designing good interfaces for AI systems to interact with humans in novel ways will become increasingly important as the systems increase in capability. We can imagine a bifurcation in the path of humankind's future: one in which we are left behind once the machines we create exceed our natural capabilities, and another in which we are uplifted along with them. We hope that this paper can further inspire the HCI community to contribute to this exciting problem of building the infrastructure for our changing future.

## Acknowledgements

We are grateful to Lav Varshney for his valuable discussions and helpful feedback and to Michael Ivanitskiy and John Balis for their feedback and help compiling this article. In addition we would like to thank Miles Brundage and OpenAI for providing access to GPT-3.

## References

[1] Espen J Aarseth. "Nonlinearity and literary theory". In: Hyper/text/theory 52 (1994), pp. 761-780.

[2] Kimberly Amaral. "Hypertext and writing: An overview of the hypertext medium". In: Retrieved August 16 (1995), p. 2004.

[3] Mark Bernstein. "Storyspace 1". In: Proceedings of the thirteenth ACM conference on Hypertext and hypermedia. 2002, pp. 172-181.

[4] Tom B Brown et al. "Language models are few-shot learners". In: arXiv preprint arXiv:2005.14165 (2020).

[5] David Deutsch. The Fabric of Reality. Penguin UK, 1998.

[6] Bryce Seligman DeWitt and Neill Graham. The many worlds interpretation of quantum mechanics. Vol. 63. Princeton University Press, 2015.

[7] Amit Gupta and James Yu. https://www.sudowrite.com/. 2021. url: https://www.sudowrite.com/ (visited on 01/14/2021).

[8] Spencer Jordan. "'An Infinitude of Possible Worlds': Towards a Research Method for Hypertext Fiction". In: New Writing 11.3 (2014), pp. 324-334.

[9] Love Lagerkvist and Maliheh Ghajargar. "Multiverse: Exploring Human Machine Learning Interaction Through Cybertextual Generative Literature". In: 10th International Conference on the Internet of Things Companion. 2020, pp. 1-6.

[10] M. O. Riedl and R. M. Young. "From linear story generation to branching story graphs". In: IEEE Computer Graphics and Applications 26.3 (2006), pp. 23-31. doi: 10.1109/MCG.2006.56.

[11] Mark Owen Riedl and Vadim Bulitko. "Interactive narrative: An intelligent systems approach". In: Ai Magazine 34.1 (2013), pp. 67-67.

[12] Paul A Roth. "The pasts". In: History and Theory 51.3 (2012), pp. 313-339.