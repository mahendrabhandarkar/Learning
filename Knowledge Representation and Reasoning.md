Knowledge Representation is organizing information in a way that computer can use to solve complex tasks.  
Reasoning is algebraically manipulating previously acquired knowledge in order to answer a new question.  

How knowledge can be represented? How knowledge can be used? How knowledge can be acquired?


  * [overview](#overview)
  * [knowledge representation](#knowledge-representation)
    - [natural language](#knowledge-representation---natural-language)
    - [knowledge graph](#knowledge-representation---knowledge-graph)  
    - [probabilistic database](#knowledge-representation---probabilistic-database)  
    - [probabilistic program](#knowledge-representation---probabilistic-program)
    - [distributed representations](#knowledge-representation---distributed-representations)
  * [reasoning](#reasoning)
    - [neural architectures](#neural-architectures)
    - [natural logic](#natural-logic)
    - [description logic](#description-logic)
    - [formal logic](#formal-logic)
    - [commonsense reasoning](#commonsense-reasoning)
  * [machine comprehension challenges](#machine-comprehension-challenges)
  * [machine reading projects](#machine-reading-projects)
  * [conferences](#conferences)
  * [books and monographies](#books-and-monographies)
  * [interesting papers](#interesting-papers)
    - [knowledge bases](#interesting-papers---knowledge-bases)
    - [knowledge bases with discrete representations](#interesting-papers---knowledge-bases-with-discrete-representations)
    - [knowledge bases with continuous representations](#interesting-papers---knowledge-bases-with-continuous-representations)
    - [continuous representations of text](#interesting-papers---continuous-representations-of-text)
    - [question answering over knowledge bases](#interesting-papers---question-answering-over-knowledge-bases)
    - [question answering over texts](#interesting-papers---question-answering-over-texts)
    - [reasoning](#interesting-papers---reasoning)
    - [information extraction and integration](#interesting-papers---information-extraction-and-integration)
    - [multimodal knowledge representation](#interesting-papers---multimodal-knowledge-representation)



---
### overview

  "The fathers of AI believed that formal logic provided insight into how human reasoning must work. For implications to travel from one sentence to the next, there had to be rules of inference containing variables that got bound to symbols in the first sentence and carried the implications to the second sentence. I shall demonstrate that this belief is as incorrect as the belief that a lightwave can only travel through space by causing disturbances in the luminiferous aether. In both cases, scientists were misled by compelling but incorrect analogies to the only systems they knew that had the required properties. Arguments have little impact on such strongly held beliefs. What is needed is a demonstration that it is possible to propagate implications in some quite different way that does not involve rules of inference and has no resemblance to formal logic. Recent results in machine translation using recurrent neural networks show that the meaning of a sentence can be captured by a "thought vector" which is simply the hidden state vector of a recurrent net that has read the sentence one word at a time. In future, it will be possible to predict thought vectors from the sequence of previous thought vectors and this will capture natural human reasoning. With sufficient effort, it may even be possible to train such a system to ignore nearly all of the contents of its thoughts and to make predictions based purely on those features of the thoughts that capture the logical form of the sentences used to express them."

  "If we can convert a sentence into a vector that captures the meaning of the sentence, then google can do much better searches, they can search based on what is being said in a document. Also, if you can convert each sentence in a document into a vector, you can then take that sequence of vectors and try and model why you get this vector after you get these vectors, that's called reasoning, that's natural reasoning, and that was kind of the core of good old fashioned AI and something they could never do because natural reasoning is a complicated business, and logic isn't a very good model of it, here we can say, well, look, if we can read every english document on the web, and turn each sentence into a thought vector, we've got plenty of data for training a system that can reason like people do. Now, you might not want to reason like people do on the web, but at least we can see what they would think."

  "Most people fall for the traditional AI fallacy that thought in the brain must somehow resemble lisp expressions. You can tell someone what thought you are having by producing a string of words that would normally give rise to that thought but this doesn't mean the thought is a string of symbols in some unambiguous internal language. The new recurrent network translation models make it clear that you can get a very long way by treating a thought as a big state vector. Traditional AI researchers will be horrified by the view that thoughts are merely the hidden states of a recurrent net and even more horrified by the idea that reasoning is just sequences of such state vectors. That's why I think its currently very important to get our critics to state, in a clearly decideable way, what it is they think these nets won't be able to learn to do. Otherwise each advance of neural networks will be met by a new reason for why that advance does not really count. So far, I have got both Garry Marcus and Hector Levesque to agree that they will be impressed if neural nets can correctly answer questions about "Winograd" sentences such as "The city councilmen refused to give the demonstrators a licence because they feared violence." Who feared the violence?"

  "There are no symbols inside the encoder and decoder neural nets for machine translation. The only symbols are at the input and output. Processing pixel arrays is not done by manipulating internal pixels. Maybe processing symbol strings is not done by manipulating internal symbol strings. It was obvious to physicists that light waves must have an aether to propagate from one place to the next. They thought there was no other possibility. It was obvious to AI researchers that people must use formal rules of inference to propagate implications from one proposition to the next. They thought there was no other possibility. What is inside the black box is not necessarily what goes in or what comes out. The physical symbol system hypothesis is probably false."

  "Most of our reasoning is by analogy; it's not logical reasoning. The early AI guys thought we had to use logic as a model and so they couldn't cope with reasoning by analogy. The honest ones, like Allen Newell, realized that reasoning by analogy was a huge problem for them, but they weren't willing to say that reasoning by analogy is the core kind of reasoning we do, and logic is just a sort of superficial thing on top of it that happens much later."

  *(Geoff Hinton)*

##

  "Where do the symbols and self-symbols underlying consciousness and sentience come from? I think they come from data compression during problem solving. While a problem solver is interacting with the world, it should store the entire raw history of actions and sensory observations including reward signals. The data is ‘holy’ as it is the only basis of all that can be known about the world. If you can store the data, do not throw it away! Brains may have enough storage capacity to store 100 years of lifetime at reasonable resolution. As we interact with the world to achieve goals, we are constructing internal models of the world, predicting and thus partially compressing the data history we are observing. If the predictor/compressor is a biological or artificial recurrent neural network (RNN), it will automatically create feature hierarchies, lower level neurons corresponding to simple feature detectors similar to those found in human brains, higher layer neurons typically corresponding to more abstract features, but fine-grained where necessary. Like any good compressor, the RNN will learn to identify shared regularities among different already existing internal data structures, and generate prototype encodings (across neuron populations) or symbols for frequently occurring observation sub-sequences, to shrink the storage space needed for the whole (we see this in our artificial RNNs all the time). Self-symbols may be viewed as a by-product of this, since there is one thing that is involved in all actions and sensory inputs of the agent, namely, the agent itself. To efficiently encode the entire data history through predictive coding, it will profit from creating some sort of internal prototype symbol or code (e.g. a neural activity pattern) representing itself. Whenever this representation becomes activated above a certain threshold, say, by activating the corresponding neurons through new incoming sensory inputs or an internal ‘search light’ or otherwise, the agent could be called self-aware. No need to see this as a mysterious process - it is just a natural by-product of partially compressing the observation history by efficiently encoding frequent observations."

  *(Juergen Schmidhuber)*

##

  "A plausible definition of "reasoning" could be "algebraically manipulating previously acquired knowledge in order to answer a new question". This definition covers first-order logical inference or probabilistic inference. It also includes much simpler manipulations commonly used to build large learning systems. For instance, we can build an optical character recognition system by first training a character segmenter, an isolated character recognizer, and a language model, using appropriate labelled training sets. Adequately concatenating these modules and fine tuning the resulting system can be viewed as an algebraic operation in a space of models. The resulting model answers a new question, that is, converting the image of a text page into a computer readable text. This observation suggests a conceptual continuity between algebraically rich inference systems, such as logical or probabilistic inference, and simple manipulations, such as the mere concatenation of trainable learning systems. Therefore, instead of trying to bridge the gap between machine learning systems and sophisticated "all-purpose" inference mechanisms, we can instead algebraically enrich the set of manipulations applicable to training systems, and build reasoning capabilities from the ground up."

  *(Leon Bottou)*

##

  "Knowledge is essential for natural language understanding. The interesting question is what knowledge should we bother to put in versus what can we learn. Foundational science behind used to be knowledge representation, and then it went away and now it is machine learning. But the truth is you need both. The question is what of which should you combine. Learning is a "knowledge lever". Deductive inference is a "knowledge lever". Better then memorization where there is no lever. But deduction is not a sufficiently powerful lever for things like NLP, because there are things like open world and long tails - deduction is not enough. Induction is an amazing lever - you got a ton of leverage out of very litte knowledge, but you need some knowledge. You can have the greatest lever but without things to push on one side the other one doesn't go up. So if you think about knowledge as a lever the question becomes what knowledge do you want to use. We want to encode high-leverage knowledge. You don't want to waste efforts encoding knowlege you can get by annotating things or just by going to the web and reading documents - that's truly a waste of time. What is high-leverage knowledge - it's one with one or both following characterists. It's hard to learn - some things you have a tons of data for, some things you don't. Some things you can learn with a greedy learner and weight optimization, some things you can't. It's the letter you really want to put in because if you don't you really miss something. And the other side of this coin is you want to put knowledge that is helpful for learning - it's not a question of knowledge or learning. You know there is free-lunch theorem which says there is no such thing as learning without knowledge. So the question is which knowledge helps learning - that's what I want to put in. You want to put a narrower effort that adds job a thousand when I add that to learning. Next thing is knowledge should be stated declaratively. Philosophically it's probably not, but from engineering point of you it's more comprehensible than knowledge that's encoded procedurally or in deep neural network (as much as we like idea of training everything together). You want something you can get a handle to get lever - you don't want something opaque, you can't work with that. Knowledge stated declaratively is also more portable (take it from one task to another), is more extensible (compose pieces of knowledge got in different ways). And the most important, it supports refinement loop in learning. Learning is not a one-shot thing - you put in some knowledge that's very weak (from SVM or decision tree) and then you run it on the data, and then you look what happens - if you don't understand what learner is giving, you can't do refinement loop. If you understand knowledge that's going in and going out, you can figure out what to change. And doing this change and relearn, and figure out what went wrong - putting the knowledge that explains what went wrong. If this is in comprehensible language the end result would be much better than if you have something opaque. What language should be used to store knowledge. Obviously, it should be natural language - there is no better language, although it is hard to deal with."

  *(Pedro Domingos)*

##

  "AI started with small data and rich semantic theories. The goal was to build systems that could reason over logical models of how the world worked; systems that could answer questions and provide intuitive, cognitively accessible explanations for their results. There was a tremendous focus on domain theory construction, formal deductive logics and efficient theorem proving. We had expert systems, rule-bases, forward chaining, backward chaining, modal logics, naïve physics, lisp, prolog, macro theories, micro theories, etc. The problem, of course, was the knowledge acquisition bottleneck; it was too difficult, slow and costly to render all common sense knowledge into an integrated, formal representation that automated reasoning engines could digest. In the meantime, huge volumes of unstructured data became available, compute power became ever cheaper and statistical methods flourished. AI evolved from being predominantly theory-driven to predominantly data-driven. Automated systems generated output using inductive techniques. Training over massive data produced flexible and capable control systems, powerful predictive engines in domains ranging from language translation to pattern recognition, from medicine to economics. Coming from a background in formal knowledge representation and automated reasoning, the writing was on the wall - big data and statistical machine learning was changing the face of AI and quickly."

  "From the very inception of IBM Watson, I put a stake in the ground; we will not even attempt to build rich semantic models of the domain. I imagined it would take 3 years just to come to consensus on the common ontology to cover such a broad domain. Rather, we will use a diversity of shallow text analytics, leverage loose and fuzzy interpretations of unstructured information. We would allow many researchers to build largely independent NLP components and rely on machine learning techniques to balance and combine these loosely federated algorithms to evaluate answers in the context of passages. The approach, with a heck of a lot of good engineering, worked. Watson was arguably the best factoid question-answering system in the world, and Watson Paths, could connect questions to answers over multiple steps, offering passage-based "inference chains" from question to answer without a single "if-then rule". But could it explain why an answer is right or wrong? Could it reason over a logical understanding of the domain? Could it automatically learn from language and build the logical or cognitive structures that enable and precede language itself? Could it understand and learn the way we do? No. No. No. No. To advance AI to where we all know it must go, we need to discover how to efficiently combine human cognition, massive data and logical theory formation. We need to boot strap a fluent collaboration between human and machine that engages logic, language and learning to enable machines to learn how to learn."

  *(David Ferucci)*

##

  "Knowledge organizes our understanding of the world, determining what we expect given what we have already seen. Our predictive representations have two key properties: they are productive, and they are graded. Productive generalization is possible because our knowledge decomposes into concepts - elements of knowledge that are combined and recombined to describe particular situations. Gradedness is the observable effect of accounting for uncertainty - our knowledge encodes degrees of belief that lead to graded probabilistic predictions. To put this a different way, concepts form a combinatorial system that enables description of many different situations; each such situation specifies a distribution over what we expect to see in the world, given what we have seen. We may think of this system as a probabilistic language of thought in which representations are built from language-like composition of concepts and the content of those representations is a probability distribution on world states. Probabilistic language of thought hypothesis (informal version): Concepts have a language-like compositionality and encode probabilistic knowledge. These features allow them to be extended productively to new situations and support flexible reasoning and learning by probabilistic inference."

  "How do humans come to know so much about the world from so little data? Even young children can infer the meanings of words, the hidden properties of objects, or the existence of causal relations from just one or a few relevant observations far outstripping the capabilities of conventional learning machines. How do they do it and how can we bring machines closer to these human-like learning abilities? I argue that people's everyday inductive leaps can be understood in terms of (approximations to) probabilistic inference over generative models of the world. These models can have rich latent structure based on abstract knowledge representations, what cognitive psychologists have sometimes called "intuitive theories", "mental models", or "schemas". They also typically have a hierarchical structure supporting inference at multiple levels, or "learning to learn", where abstract knowledge may itself be learned from experience at the same time as it guides more specific generalizations from sparse data. I focus on models of learning and "learning to learn" about categories, word meanings and causal relations. I can show in each of these settings how human learners can balance the need for strongly constraining inductive biases necessary for rapid generalization with the flexibility to adapt to the structure of new environments, learning new inductive biases for which our minds could not have been pre-programmed."

  "How can we build machines that learn the meanings of words more like the way that human children do? Children can learn words from minimal data, often just one or a few positive examples (one-shot learning). Children learn to learn: they acquire powerful inductive biases for new word meanings in the course of learning their first words. Children can learn words for abstract concepts or types of concepts that have little or no direct perceptual correlate. Children's language can be highly context-sensitive, with parameters of word meaning that must be computed anew for each context rather than simply stored. Children learn function words: words whose meanings are expressed purely in how they compose with the meanings of other words. Children learn whole systems of words together, in mutually constraining ways, such as color terms, number words, or spatial prepositions. Children learn word meanings that not only describe the world but can be used for reasoning, including causal and counterfactual reasoning. Bayesian learning defined over appropriately structured representations - hierarchical probabilistic models, generative process models, and compositional probabilistic languages - provides a basis for beginning to address these challenges."

  "If our goal is to build knowledge representations sufficient for human-level AI, it is natural to draw inspiration from the content and form of knowledge representations in human minds. Cognitive science has made significant relevant progress in the last several decades, and I can talk about several lessons AI researchers might take from it. First, rather than beginning by trying to extract commonsense knowledge from language, we should begin (as humans do) by capturing in computational terms the core of common sense that exists in prelinguistic infants, roughly 12 months and younger. This is knowledge about physical objects, intentional agents, and their causal interactions -- an intuitive physics with concepts analogous to force, mass and the dynamics of motion, and an intuitive psychology with concepts analogous to beliefs, desires and intentions, or probabilistic expectations, utilities and plans -- which is grounded in perception but has at its heart powerful abstractions that can extend far beyond our direct perceptual experience. Second, we should explore approaches for linguistic meaning, language understanding and language-based common-sense reasoning that build naturally on top of this common-sense core. Both of these considerations strongly favor an approach to knowledge representation based on probabilistic programs, a framework that combines the assets of traditional probabilistic and symbolic approaches."

  *(Josh Tenenbaum)*



---
### knowledge representation

  - [natural language](#knowledge-representation---natural-language)
  - [knowledge graph](#knowledge-representation---knowledge-graph)
  - [probabilistic database](#knowledge-representation---probabilistic-database)
  - [probabilistic program](#knowledge-representation---probabilistic-program)
  - [distributed representations](#knowledge-representation---distributed-representations)



---
### knowledge representation - natural language

  "AI requires a lot of knowledge. Reading is the easiest way to acquire it. Text is rich but messy."

  "A machine comprehends a passage of text if, for any question regarding that text that can be answered correctly by a majority of native speakers, that machine can provide a string which those speakers would agree both answers that question, and does not contain information irrelevant to that question."

  *(Ludwig Wittgenstein)* "The language is meant to serve for communication between a builder A and an assistant B. A is building with building-stones: there are blocks, pillars, slabs and beams. B has to pass the stones, and that in the order in which A needs them. For this purpose they use a language consisting of the words “block”, “pillar”, “slab”, “beam”. A calls them out - B brings the stone which he has learnt to bring at such-and-such a call. Conceive this as a complete primitive language."  
  *(Jon Gauthier)* "This game is not just a game of words but a game of words causing things and of other things causing words. We can’t fully define the meaning of a word like “slab” without referring to the physical actions of A and B. In this way, linguistic meaning has to bottom out at some point in nonlinguistic facts."

  *(Joseph Weizenbaum, creator of ELIZA chat bot)* "No general solution to the problem of computer understanding of natural language is possible, i.e. language is understood only in contextual frameworks, that even these can be shared by people to only a limited extent, and that consequently even people are not embodiments of any such general solution."

##

  [Natural Language Processing](https://dropbox.com/s/0kw1s9mrrcwct0u/Natural%20Language%20Processing.txt)

  ["A Paradigm for Situated and Goal-Driven Language Learning"](https://arxiv.org/abs/1610.03585) by Jon Gauthier and Igor Mordatch  
>	"We outlined a paradigm for grounded and goal-driven language learning in artificial agents. The paradigm is centered around a utilitarian definition of language understanding, which equates language understanding with the ability to cooperate with other language users in real-world environments. This position demotes language from its position as a separate task to be solved to one of several communicative tools agents might use to accomplish their real-world goals."

  ["Solving Language"](http://foldl.me/2016/solving-language/) + ["Situated Language Learning"](http://foldl.me/2016/situated-language-learning/) by Jon Gauthier


  ["Natural Language Understanding: Foundations and State-of-the-Art"](http://youtube.com/watch?v=mhHfnhh-pB4) by Percy Liang

  ["A Survey of the Current State of Reading Comprehension"](http://matt-gardner.github.io/paper-thoughts/2016/12/08/reading-comprehension-survey.html) by Matt Gardner



---
### knowledge representation - knowledge graph

#### Entity-Attribute-Value model (RDF) with Classes and Relationships (OWL)

  [overview](https://dropbox.com/s/ono4n5yij0y1366/RDF.txt)  
  [interesting papers](https://dropbox.com/sh/c427b94xex62a40/AABii9_MRHrCZPGJ_Adx_b3Ma)  

  ["Ontologies and Knowledge Representation"](https://lektorium.tv/course/22781) course by Boris Konev (in russian)


  ["Schema.org: Evolution of Structured Data on the Web"](http://queue.acm.org/detail.cfm?id=2857276)  
>	"We report some key schema.org adoption metrics from a sample of 10 billion pages from a combination of the Google index and Web Data Commons. In this sample, 31.3% of pages have schema.org markup, up from 22% one year ago. Structured data markup is now a core part of the modern web."


  RDF on the web with schema.org types as the largest existing structured knowledge base - http://youtube.com/watch?v=-UljtBjV8jM (Guha)
>	"I don't think we even have the begginings of theory [filtering, entity resolution, graph reconciliation]"


  problems of RDF on the web:
  - strong assumptions (nothing is ever wrong, no contradictions)
  - outdated, incorrect or incomplete data
  - mistakes made by tools (noisy information extraction, entity linking/reconciliation)
  - limited or no reuse of identifiers
  - metadata not always representative of content

##

### Relational Machine Learning (on knowledge graphs)

  traditional ML: data = matrix  
  relational ML:
  - multiple data sources, different tuples of variables
  - share representations of same types across data sources
  - shared learned representations help propagate information among data sources

  problems:
  - *link prediction/mining*:  predicting whether or not two or more objects are related  *[graph completion]*
  - *link-based clustering*:  grouping of similar objects, where similarity is determined according to the links of an object, and the related task of collaborative filtering, i.e. the filtering for information that is relevant to an entity (where a piece of information is considered relevant to an entity if it is known to be relevant to a similar entity)  *[entity reconciliation, taxonomy learning]*
  - *object classification*:  (simultaneous) prediction of the class of several objects given objects' attributes and their relations  *[defining type, schema matching]*
  - *object identification*:  identification of equivalent entries in two or more separate databases/datasets  *[entity linking, ontology mapping]*


  Concerned with models of domains that exhibit both uncertainty (which can be dealt with using statistical methods) and complex, relational structure.  
  Combines machine learning with relational data models and first-order logic and enables machine learning in knowledge bases.  
  Knowledge representation formalisms use (a subset of) first-order logic to describe relational properties of a domain in a general manner (universal quantification) and draw upon probabilistic graphical models (such as Bayesian networks or Markov networks) to model the uncertainty.  
  Not strictly limited to learning aspects - equally concerned with reasoning (specifically probabilistic inference) and knowledge representation.  

##

  "Statistical Relational Learning" tutorial by Tresp - http://videolectures.net/mlpmsummerschool2014_tresp_statistical_learning/

  "A Review of Relational Machine Learning for Knowledge Graphs: From Multi-Relational Link Prediction to Automated Knowledge Graph Construction"
	by Nickel, Murphy, Tresp, Gabrilovich - http://arxiv.org/abs/1503.00759

  "Constructing and Mining Web-Scale Knowledge Graphs" tutorial by Gabrilovich and Bordes -
	http://videolectures.net/kdd2014_gabrilovich_bordes_knowledge_graphs/

##

  "Multi-relational learning can be categorized into three categories:
  - *statistical relational learning* which directly encodes multi-relational graphs using probabilistic models such as Markov Logic Networks
  - *path ranking method* which explicitly explores the large relational feature space of relations with random walk
  - *embedding-based models* which embed multi-relational knowledge into low-dimensional representations of entities and relations via tensor/matrix factorization, Bayesian clustering framework or neural networks."

  history of approaches:
  - tensor factorization (Harshman'94)
  - probabilistic relational learning (Friedman'99)
  - relational Markov networks (Taskar'02)
  - Markov logic networks (Kok'07)
  - spectral clustering (undirected graphs) (Dong'12)
  - ranking of random walks (Lao'11)
  - collective matrix factorization (Nickel'11)
  - matrix factorization & universal schema (Riedel'13)
  - embedding models (Bordes'11)

##

#### random walk inference

  Path Ranking Algorithm *(used in [Google Knowledge Vault](https://youtu.be/i2r5J4XAhsw?t=5m7s) and NELL)* -
	http://cs.cmu.edu/~nlao/publication/2012/defense.pdf

  subgraph feature extraction as improvement over PRA by Matt Gardner *(used in NELL)* -
	http://youtube.com/watch?v=dp2waL7OLbI + https://www.cs.cmu.edu/~mg1/paper.pdf  
  "Reading and Reasoning with Knowledge Graphs" thesis by Matt Gardner -
	http://www.cs.cmu.edu/~mg1/thesis.pdf  

  PRA with distributed representations and Recurrent Neural Network *(used in Epistemological database)* -
	http://youtube.com/watch?v=mSrkzc0Nksg + https://docs.google.com/file/d/0B_hicYJxvbiOTUxZMWY5T2N2VG8

  PRA over proof space for first-order logic *(used in ProPPR)* -
	http://youtu.be/--pYaISROqE?t=12m35s + https://drive.google.com/file/d/0B_hicYJxvbiOc05xNEhvdVVSQWc

##

#### continuous embeddings

  overview by Antoines Bordes - http://videolectures.net/kdd2014_gabrilovich_bordes_knowledge_graphs/ (part 2, 1:07:43)  
  overview by Jason Weston - http://youtube.com/watch?v=FVjuwv1_EDw  

  used in Google Knowledge Vault  
	http://youtu.be/i2r5J4XAhsw?t=3m7s  
	http://videolectures.net/mlpmsummerschool2014_tresp_statistical_learning/ (part 2, 1:19:37)  
	http://arxiv.org/abs/1503.00759  

  implementations of DistMult, Model E, Model F, Model N, Model O - https://github.com/dirkweissenborn/genie-kb/blob/master/model/models.py

  [distributed representations](https://github.com/brylevkirill/notes/blob/master/Deep%20Learning.md#distributed-representations)

##

#### latent factor models

  with latent features one gets collective learning - information can globally propagate in the network of random variables

  http://videolectures.net/kdd2014_gabrilovich_bordes_knowledge_graphs/ (part 2, 1:00:12)

##

#### matrix factorization of universal schema

  overview by Andrew McCallum -  
	http://yahoolabs.tumblr.com/post/113969611311/big-thinker-andrew-mccallum-discusses-the  
	http://videolectures.net/akbcwekex2012_mccallum_base_construction/  

  - unifying traditional canonical relations, such as those of the Freebase schema, with OpenIE surface form patterns in a universal schema
  - completing a knowledge base of such a schema using matrix factorization

  *advantage*:  for canonical relations it effectively performs distant supervision and hence requires no textual annotations  
  *advantage*:  in the spirit of OpenIE, a universal schema can use textual patterns as novel relations and hence increases the coverage of traditional schemas  
  *advantage*:  matrix factorization learns better embeddings for entity-pairs for which only surface form patterns are observed, and these can also lead to better extractions of canonical relations  

  logic embedding (combining with knowledge represented as first-order logic) -  
 	http://techtalks.tv/talks/injecting-logical-background-knowledge-into-embeddings-for-relation-extraction/61526/  
	http://rockt.github.io/slides/2015-naacl.pdf  

  [Epistemological Database](#epistemological-database)

##

#### tensor factorization of knowledge graph

  Machine Learning with Knowledge Graphs" by Volker Tresp -
	http://videolectures.net/eswc2014_tresp_machine_learning/ + http://www.dbs.ifi.lmu.de/~tresp/papers/ESWC-Keynote.pdf

  "Machine Learning on Linked Data: Tensors and Their Applications In Graph-Structured Domains" - http://www.cip.ifi.lmu.de/~nickel/iswc2012-slides/#/  
  "Tensor Factorization for Relational Learning" (RESCAL model) - http://edoc.ub.uni-muenchen.de/16056/1/Nickel_Maximilian.pdf  

  "Towards Combined Matrix and Tensor Factorization for Universal Schema Relation Extraction" - https://rockt.github.io/pdf/singh2015towards.pdf

##

#### Mixture models

  *advantage*:  no need for good prior knowledge about relational dependencies as in bayes nets and markov nets  
  *advantage*:  great simplicity of the model: no need to think about rules, conditional independencies, loops or global partition functions  

##

#### Bayesian network

  works well if there is a prior knowledge about possible candidates for relational dependencies

  *disadvantage*:  it is difficult to avoid loops in the ground Bayes net with symmetric relations such as friendOf  
  *disadvantage*:  as always in bayes nets, one needs to define a complete system, i.e. conditional probabilities for each node in the ground bayes net (which can be demanding)  
  both problems can be solved with Markov Logic Network  

##

#### Markov network

  typically better suited for modeling symmetric interactions (e.g. friendOf) - no concern about directed loops

  *advantage*:  do not need to be complete - "Just model what you know about, the rest is filled in with maximum entropy"  
  *disadvantage*:  maximum likelihood learning with complete data is already non-trivial  
  *disadvantage*:  no causal interpretation  

##

**Markov Logic Network**

  - MLN does not require local normalization, i.e. an interpretation of the terms as local conditional probabilities - it requires global normalization
  - in MLN one can use any FOL formula, not just the ones derived from bayes nets
  - MLN does not require a specific number of formulae
  - in MLN no problem if a formula is sometimes false, formula weight corresponds to degree that formula is supported in the training data
  - formulae can be derived using ILP techniques (FOIL, Claudian)

  *advantage*:  no need to worry about directed loops or parameter constraints  
  *advantage*:  no need to worry about completeness, there can be any number of formulae (from none to more than there are ground atoms) - with no formulae each configuration of node states has the same probability (maximum entropy principle)  
  *disadvantage*:  no interpretation of local conditional distribution (no causal interpretation)  
  *disadvantage*:  difficult parameter learning (unlike in bayes nets with complete data) due to global normalization constant (sum over all states) - typical approach: closed-world assumption and optimization of a pseudo-likelihood  

  [Markov Logic Network](#markov-logic-network)



---
### knowledge representation - probabilistic database

  "A probabilistic database is a relational database in which the tuples stored have associated uncertainties. That is, each tuple t has an associated indicator random variable Xt which takes a value 1 if the tuple is present in the database and 0 if the tuple is absent. Each instantiation of values to all of the random variables is called a world. The probabilistic database is the joint probability distribution over the random variables, which implicitly specifies a distribution over all the possible worlds. The answer to a query Q on a probabilistic database is the set of tuples T that are possible answers to Q, along with a probability P(t) for every t ∈ T denoting the probability that t belongs the answer for query Q. A probabilistic database together with a query can be encoded as a probabilistic program, and the answer to query evaluation can be phrased as probabilistic inference. Work in probabilistic databases has identified a class of queries (called safe queries) for which query evaluation can be performed efficiently, by pushing the probabilistic inference inside particular query plans (called safe plans)."

  Suciu, Olteanu, Re, Koch - ["Probabilistic Databases"](http://www.dblab.ntua.gr/~gtsat/collection/Morgan%20Claypool/Probabilistic%20Databases%20-%20Dan%20Suciu%20-%20Morgan%20Clayman.pdf)
>	"Probabilistic databases are databases where the value of some attributes or the presence of some records are uncertain and known only with some probability. Applications in many areas such as information extraction, RFID and scientific data management, data cleaning, data integration, and financial risk assessment produce large volumes of uncertain data, which are best modeled and processed by a probabilistic database. This book presents the state of the art in representation formalisms and query processing techniques for probabilistic data. It starts by discussing the basic principles for representing large probabilistic databases, by decomposing them into tuple-independent tables, block-independent-disjoint tables, or U-databases. Then it discusses two classes of techniques for query evaluation on probabilistic databases. In extensional query evaluation, the entire probabilistic inference can be pushed into the database engine and, therefore, processed as effectively as the evaluation of standard SQL queries. The relational queries that can be evaluated this way are called safe queries. In intensional query evaluation, the probabilistic inference is performed over a propositional formula called lineage expression: every relational query can be evaluated this way, but the data complexity dramatically depends on the query being evaluated, and can be #P-hard. The book also discusses some advanced topics in probabilistic data management such as top-k query processing, sequential probabilistic databases, indexing and materialized views, and Monte Carlo databases."

  https://en.wikipedia.org/wiki/Probabilistic_logic
>	"The aim of a probabilistic logic is to combine the capacity of probability theory to handle uncertainty with the capacity of deductive logic to exploit structure. The result is a richer and more expressive formalism with a broad range of possible application areas."

  ["10 Years of Probabilistic Querying - What Next?"](https://lirias.kuleuven.be/bitstream/123456789/403578/1/theobald-adbis13.pdf)

##

  - [Epistemological Database](#probabilistic-database---epistemological-database)
  - [Markov Logic Network](#probabilistic-database---markov-logic-network)
  - [Probabilistic Soft Logic](#probabilistic-database---probabilistic-soft-logic)
  - [ProPPR](#probabilistic-database---proppr)

##

### probabilistic database - Epistemological Database

  Andrew McCallum -  
	["Universal Schema for Representation and Reasoning from Natural Language"](http://www.fields.utoronto.ca/video-archive/2016/11/2267-16181)  
	["Construction of Probabilistic Databases for Large-scale Knowledge Bases"](http://yahoolabs.tumblr.com/post/113969611311/big-thinker-andrew-mccallum-discusses-the)  
	["Representation and Reasoning with Universal Schema Embeddings"](http://videolectures.net/iswc2015_mccallum_universal_schema/)  
	["Knowledge Base Construction with Epistemological Databases"](http://videolectures.net/akbcwekex2012_mccallum_base_construction/)  
	["FACTORIE: A Scala Library for Machine Learning & NLP"](http://youtube.com/watch?v=MEhN9K36BfQ)  

  Limin Yao -  
	["Universal Schema for Knowledge Representation from Text and Structured Data"](https://youtube.com/watch?v=odI3RznREY4)

  implementation: http://factorie.cs.umass.edu

##

  - information extraction with joint inference
  - probabilistic databases to manage uncertainty at scale
  - robust reasoning about human edits
  - tight integration of probabilistic inference and parallel distributed processing
  - probabilistic programming languages for easy specification of complex factor graphs

  problems:
  - how to represent & inject uncertainty from IE into DB?
  - want to use DB contents to aid IE
  - IE isn't one-shot: add new data later - redo inference
  - want DB infrastructure to manage IE

  challenges:
  - postpone decision making until all data is available
  - inject knowledge into machine reading
  - derive true facts from raw evidence data

##

  epistemological KB: "truth is inferred, not observed"
  - entities/relations never input, only "mentions"
  - ability to change our mind about previously made (wrong) decisions

  human edits as evidence:
  - traditional: change db record of truth
  - mini-document "Nov 15: Scott said this was true"
  - sometimes humans are wrong, disagree, out-of-date -> jointly reason about truth & editors' reliability/reputation

  never ending inference (constantly bubbling in background):
  - traditional: KB entries locked in
  - KB entries always reconsidered with more evidence, time

##

  entity resolution:
  - foundational, not just for coreference of entity-mentions
  - align values, ontologies, schemas, relations, events
  - joint entity linking (identifying group of mentions in document) and entity discovery (identifying cluster of mentions across documents)  

  styles of relation extraction:
  - supervised
  - distantly supervised
  - unsupervised (no schema, OpenIE)
  - unsupervised (schema discovery)
  - universal schema

##

  probabilistic db with universal schema:
  - schema = union of all inputs: natural langauge & databases
    * embrace diversity and ambiguity of original inputs
    * don't try to force semantics into pre-defined boxes
    * note: combining "structured" & "natural" schema
  - learn implicature among entity-relations
    * "fill in" unobserved relations
    * implicit alignment of "structured" & "natural"

##

  low-dimensional embeddings of logic:

  "Many machine reading approaches, from shallow information extraction to deep semantic parsing, map natural language to symbolic representations of meaning. Representations such as first-order logic capture the richness of natural language and support complex reasoning, but often fail in practice due to their reliance on logical background knowledge and the difficulty of scaling up inference. In contrast, low-dimensional embeddings (i.e. distributional representations) are efficient and enable generalization, but it is unclear how reasoning with embeddings could support the full power of symbolic representations such as first-order logic. In this proof-of-concept paper we address this by learning embeddings that simulate the behavior of first-order logic."

  http://techtalks.tv/talks/injecting-logical-background-knowledge-into-embeddings-for-relation-extraction/61526/

  http://yoavartzi.com/sp14/slides/rockt.sp14.pdf  
  https://b8ca8e88-a-62cb3a1a-s-sites.googlegroups.com/site/learningsemantics2014/SebastianRiedel.pdf  

##

### probabilistic database - Markov Logic Network

  superset of first-order logic and undirected graphical models

  (Josh Tenenbaum) "There was something really right about logic. It wasn't deductive inference which is too weak and brittle but abstraction. And if we combine abstraction of predicate logic with power of statistical learning and inference, we can do some pretty cool things."


  Pedro Domingos  
	["Unifying Logical and Statistical AI"](http://youtube.com/watch?v=bW5DzNZgGxY)  
	["Combining Logic and Probability: Languages, Algorithms and Applications"](http://videolectures.net/uai2011_domingos_kersting_combining/)  
	["Incorporating Prior Knowledge into NLP with Markov Logic"](http://videolectures.net/icml08_domingos_ipk/)  
	["Machine Learning for the Web: A Unified View"](http://videolectures.net/bsciw08_domingos_mlwuv/)  
	["Statistical Modeling of Relational Data"](http://videolectures.net/kdd07_domingos_smord/)  

  overview by Volker Tresp - http://videolectures.net/mlpmsummerschool2014_tresp_statistical_learning/ (part 2)


  ["What’s Missing in AI: The Interface Layer"](http://homes.cs.washington.edu/~pedrod/papers/ai100.pdf) by Pedro Domingos

  ["Markov Logic: An Interface Layer for Artificial Intelligence"](http://morganclaypool.com/doi/abs/10.2200/S00206ED1V01Y200907AIM007) by Pedro Domingos, Daniel Lowd
>	"Most subfields of computer science have an interface layer via which applications communicate with the infrastructure, and this is key to their success (e.g., the Internet in networking, the relational model in databases, etc.). So far this interface layer has been missing in AI. First-order logic and probabilistic graphical models each have some of the necessary features, but a viable interface layer requires combining both. Markov logic is a powerful new language that accomplishes this by attaching weights to first-order formulas and treating them as templates for features of Markov random fields. Most statistical models in wide use are special cases of Markov logic, and first-order logic is its infinite-weight limit. Inference algorithms for Markov logic combine ideas from satisfiability, Markov chain Monte Carlo, belief propagation, and resolution. Learning algorithms make use of conditional likelihood, convex optimization, and inductive logic programming."

  ["Probabilistic Inference and Factor Graphs"](http://deepdive.stanford.edu/doc/general/inference.html)

  ["Markov Logic"](http://homes.cs.washington.edu/~pedrod/papers/pilp.pdf) by Domingos, Kok, Lowd, Poon, Richardson, Singla

##

  "Markov Logic Networks use weighted first order logic formulas to construct probabilistic models, and specify distributions over possible worlds. Markov Logic Networks can also be encoded as probabilistic programs."  
  "Most learning algorithms only look at a single relation - a single table of data - and this is very limiting. Real databases have many relations, and we want to mine straight from them. This requires a pretty substantial rethink of how to do statistical learning, because samples are no longer independent and identically distributed, due to joins, etc. The solution in Markov logic networks is to use first-order logic to express patterns among multiple relations - which it can easily do - but treat logical formulas as features in a Markov network or log-linear model, which sets up a probability distribution over relational databases that we can then use to answer questions. The goal is to provide for machine learning and data mining something akin to what the relational model and SQL provide for databases."  
  "Logical AI has focused mainly on complexity of the real world while statistical AI on uncertainty. Markov logic combines the two by attaching weights to first-order formulas and viewing them as templates for features of Markov networks. Inference algorithms for Markov logic draw on ideas from satisfiability, Markov chain Monte Carlo and knowledge-based model construction. Learning algorithms are based on the voted perceptron, pseudo-likelihood and inductive logic programming."  

##

  "Markov Logic Networks represent uncertainty in terms of weights on the logical rules as in the example:  
	∀x. Smoke(x) ⇒ Cancer(x) | 1.5  
	∀x.y Friend(x, y) ⇒ (Smoke(x) ⇔ Smoke(y)) | 1.1  
  The example states that if someone smokes, there is a chance that they get cancer, and the smoking behaviour of friends is usually similar. Markov logic uses such weighted rules to derive a probability distribution over possible worlds through an undirected graphical model. This probability distribution over possible worlds is then used to draw inferences. Weighting the rules is a way of softening them compared to hard logical constraints and thereby allowing situations in which not all clauses are satisfied.  
  With the weighted rules, a set of constants need to be specified. We can add constants representing two persons, Anna (A) and Bob (B). Probabilistic logic uses the constants to “ground” atoms with variables, so we get “ground atoms” like Smoke(A), Smoke(B), Cancer(A), Cancer(B), Friend(A, A), Friend(A, B), Friend(B, A), Friend(B, B). Rules are also grounded by replacing each atom with variables by all its possible ground atoms.  
  MLNs take as input a set of weighted first-order formulas F = F1, ..., Fn. They then compute a set of ground literals by grounding all predicates occurring in F with all possible constants in the system. Next, they define a probability distribution over possible worlds, where a world is a truth assignment to the set of all ground literals. The probability of a world depends on the weights of the input formulas F as follows: The probability of a world increases exponentially with the total weight of the ground clauses that it satisfies. The probability of a given world x is defined as:  
	P(X = x) = 1/Z * exp(Sum over i(wi * ni(x)))  
  where Z is the partition function, i ranges over all formulas Fi in F, wi is the weight of Fi, and ni(x) is the number of groundings of Fi that are true in the world x.  
  This probability distribution P(X = x) over possible worlds is computed using a Markov network, an undirected graphical model (hence the name Markov Logic Networks). In this Markov network, the nodes are the ground literals, and two nodes are connected by an edge if they co-occur in a ground clause, such that the cliques in the network correspond to ground clauses. A joint assignment of values to all nodes in the graph is a possible world, a truth assignment to the ground literals.  
  In addition to the set R of weighted formulas, an MLN takes an evidence set E asserting some truth values about some of the random variables, e.g. Cancer(A) means that Anna has cancer. Marginal inference for MLNs calculates the probability P(Q|E, R) for a query formula Q."  

  "MLNs make the Domain Closure Assumption: The only models considered for a set F of formulas are those for which the following three conditions hold. (a) Different constants refer to different objects in the domain, (b) the only objects in the domain are those that can be represented using the constant and function symbols in F, and (c) for each function f appearing in F, the value of f applied to every possible tuple of arguments is known, and is a constant appearing in F. Together, these three conditions entail that there is a one-to-one relation between objects in the domain and the named constants of F. When the set of all constants is known, it can be used to ground predicates to generate the set of all ground literals, which then become the nodes in the graphical model. Different constant sets result in different graphical models. If no constants are explicitly introduced, the graphical model is empty (no random variables)."

  "In Markov Logic, possible worlds or interpretations (i.e., truth value assignments to ground atoms) become less likely as they violate more groundings of soft constraints, and have probability zero if they violate some grounding of a hard constraint. It is well known that the transitive closure of a binary relation cannot be represented in first order logic, but requires second order constructs. Thus, the hard constraints in a Markov Logic network, which form a first order logic theory, cannot enforce probability zero for all worlds that do not respect the transitive closure of a binary relation. On the other hand, the least Herbrand semantics of definite clause logic (i.e., pure Prolog) naturally represents such transitive closures. For instance, under the least Herbrand semantics, path(A, C) :− edge(A, C). path(A, C) :− edge(A, B), path(B, C). inductively defines path as the transitive closure of the relation edge, that is, a ground atom path(a, c) is true if and only if there is a sequence of true edge atoms connecting a and c. Note that an MLN that maps the definition above to the hard constraints edge(A, C) → path(A, C). edge(A, B) ∧ path(B, C) → path(A, C) enforces the transitivity property, as these rules are violated if there is a sequence of edges connecting two nodes, but the corresponding path atom is false. Still, these hard constraints do not correspond to the transitive closure, as they can for instance be satisfied by setting all ground path atoms to true, independently of the truth values of edge atoms."

##

  - set of weighted clauses in FOPL
  - larger weight indicates stronger belief that the clause should hold
  - learning weights for an existing set of clauses with undefined weights
  - learning logical clauses (aka structure learning)
  - MLNs are templates for constructing Markov networks for a given set of constants
  - possible world becomes exponentially less likely as the total weight of all the grounded clauses it violates increases
  - infer probability of a particular query given a set of evidence facts

  advantages:
  - fully subsumes FOPL (just give infinite weight to all clauses)
  - fully subsumes probabilistic graphical models (can represent any joint distribution over an arbitrary set of discrete random variables)
  - can utilize prior knowledge in both symbolic and probabilistic forms
  - inherits computational intractability of general methods for both logical and probabilistic inference and learning: inference in FOPC is semi-decidable, inference in general graphical models is P-space complete

##

  Tractable Markov Logic  

  (Pedro Domingos) "I'm working on Markov logic networks, with an emphasis on scaling them up to big data. Our approach is to use tractable subsets of Markov logic, in the same way that SQL is a tractable subset of first-order logic. One of our current projects is to build something akin to Google's knowledge graph, but much richer, based on data from Freebase, DBpedia, etc. We call it a Tractable Probabilistic Knowledge Base - and it can answer questions about the entities and relations in Wikipedia, etc. We're planning to make a demo version available on the Web, and then we can learn from users' interactions with it."

  overview by Pedro Domingos - http://youtube.com/watch?v=6ZJzfRdCZjc

  "Tractable Probabilistic Knowledge Base: Wikipedia and Beyond" - http://aaai.org/ocs/index.php/WS/AAAIW14/paper/download/8722/8239  
  "Learning and Inference in Tractable Probabilistic Knowledge Bases" - http://homes.cs.washington.edu/~pedrod/papers/uai15.pdf  

##

  application to question answering by AI2 - http://arxiv.org/abs/1507.03045 + http://akbc.ws/2014/slides/etzioni-nips-akbc.pdf (slides 30-37)  
  application to information extraction, integration and curation by DeepDive - http://deepdive.stanford.edu/doc/advanced/markov_logic_network.html  

##

  implementations:

  - [Alchemy](http://alchemy.cs.washington.edu)

  - [Alchemy Lite](http://alchemy.cs.washington.edu/lite/)  
	scales to millions of entities  
	sublinear in size time for inference  
	linear in size time for learning  

  - [Tuffy](http://i.stanford.edu/hazy/hazy/tuffy/)  
	["Tuffy: Scaling up Statistical Inference in Markov Logic Networks using an RDBMS"](http://cs.stanford.edu/people/chrismre/papers/tuffy.pdf)  

  - [TuffyLite](https://github.com/allenai/tuffylite)  

  - [LoMRF](https://github.com/anskarl/LoMRF)  

  - [RockIt](https://code.google.com/p/rockit/)

  - [thebeast](https://code.google.com/p/thebeast/)

  - [ProbKB](http://dsr.cise.ufl.edu/tag/probkb/)  
	["Web-Scale Knowledge Inference Using Markov Logic Networks"](https://cise.ufl.edu/~yang/doc/slg2013.pdf)  

##

### probabilistic database - Probabilistic Soft Logic

  probability distribution over possible worlds

  "PSL uses first order logic rules as a template language for graphical models over random variables with soft truth values from the interval [0, 1]. This allows one to directly incorporate similarity functions, both on the level of individuals and on the level of sets. For instance, when modeling opinions in social networks, PSL allows one to not only model different types of relations between users, such as friendship or family relations, but also multiple notions of similarity, for instance based on hobbies, beliefs, or opinions on specific topics. Technically, PSL represents the domain of interest as logical atoms. It uses first order logic rules to capture the dependency structure of the domain, based on which it builds a joint probabilistic model over all atoms. Each rule has an associated non-negative weight that captures the rule’s relative importance. Due to the use of soft truth values, inference (most probable explanation and marginal inference) in PSL is a continuous optimization problem, which can be solved efficiently."
  "Also, in PSL the formula syntax is restricted to rules with conjunctive bodies."

  - input: set of weighted FOPL rules and a set of evidence (just as in MLN)
  - MAP/MPE inference is a linear optimization problem that can efficiently draw probabilistic conclusions (in MLN combinatorial counting problem)
  - atoms have continuous truth values in [0, 1]  (in MLN atoms have boolean values {0, 1})
  - inference finds truth value of all atoms that best satisfy the rules and evidence  (in MLN inference finds probability of atoms given the rules and evidence)
  - MPE inference: Most Probable Explaination  (in MLN calculates conditional probability of a query atom given evidence)

##

  http://psl.cs.umd.edu

  https://github.com/linqs/psl/wiki/Introduction-to-probabilistic-soft-logic

  Lise Getoor - https://youtube.com/watch?v=1lwGKhFAXU0  
  Raymond Mooney - http://youtube.com/watch?v=GhBHRhIsQIE  
  Jay Pujara - http://youtube.com/watch?v=z_VzaNy36xE  

  implementation: https://github.com/linqs/psl

##

### probabilistic database - ProPPR

  graph-algorithm inferences over local groundings of first-order logic programs

  William Cohen - http://youtu.be/--pYaISROqE?t=12m35s + http://www.cs.cmu.edu/afs/cs/Web/People/wcohen/nlu-2014.ppt

  "First-order probabilistic language which allows approximate “local groundings” for answering query to be constructed in time independent of database size. Extension to Stochastic Logic Programs that is biased towards short derivations; it is also closely related to an earlier relational learning algorithm called the Path Ranking Algorithm. Problem of constructing proofs for this logic is related to computation of Personalized PageRank on a linearized version of the proof space. It has proveably-correct approximate grounding scheme, based on the PageRank-Nibble algorithm, and fast and easily-parallelized weight-learning algorithm. Learning for ProPPR is orders magnitude faster than learning for Markov Logic Networks. Allows mutual recursion (joint learning) in KB inference. Can learn weights for a mutually recursive program with hundreds of clauses, which define scores of interrelated predicates, over a KB containing one million entities."

  - efficient first-order probabilistic logic, tractable and faster alternative to MLN
  - Program + DB + Query define a proof graph, where nodes are conjunctions of goals and edges are labeled with sets of features
  - queries are "locally grounded", i.e. converted to a small O(1/alpha epsilon) subset of the full KB
  - ProPPR ~ first-order version and strict generalization of Path Ranking Algorithm (Random Walks with Reset over proof trees)
  - inference is a random-walk process on a graph (with edges labeled with feature-vectors derived from KB/queries)
  - transition probabilities, Pr(child|parent), plus Personalized PageRank (aka Random Walk with Reset) define a distribution over nodes
  - transition probabilities, Pr(child|parent), are defined by weighted sum of edge features, followed by normalization
  - consequence: inference is fast, even for large KBs, and parameter learning can be parallelized
  - parameter learning improves from hours to seconds, and scales KBs from thousands of entities to millions of entities

  comparison to Markov Logic Network:
  - formalization (MLN: easy)
  - first-order program + (plugged) database of facts (MLN: clausal 1st-order logic, very expressive) (ProPPR: function)
  - "compilation" (MLN: expensive, grows with DB size) (ProPPR: fast, sublinear in DB size)
  - "compiled" representation (MLN: undirected graphical model) (ProPPR: graph with feature-vector labeled edges)
  - inference (MLN: approximate, intractable) (ProPPR: Personalized PageRank aka Random Walk with Reset, linear)
  - learning (MLN: approximate, intractable) (ProPPR: pSGD, fast but non-convex, can parallelize)

  scales to 10^5-10^6 facts and requires 10^3 training queries

  https://github.com/TeamCohen/ProPPR



---
### knowledge representation - probabilistic program

  [Probabilistic Programming](https://github.com/brylevkirill/notes/blob/master/Probabilistic%20Programming.md)


  "Concepts in a Probabilistic Language of Thought" by Goodman, Tenenbaum, Gerstenberg -
	https://web.stanford.edu/~ngoodman/papers/ConceptsChapter-final.pdf

  Josh Tenenbaum  
	["Cognitive Foundations for Common-sense Knowledge Representation and Reasoning"](https://youtube.com/watch?v=oSAG57plHnI)  
	["Building Machines That Learn Like Humans"](https://youtube.com/watch?v=quPN7Hpk014)  
	["Towards More Human-like Machine Learning of Word Meanings"](http://techtalks.tv/talks/towards-more-human-like-machine-learning-of-word-meanings/54913/)  
	["How to Grow a Mind: Statistics, Structure, and Abstraction"](http://videolectures.net/aaai2012_tenenbaum_grow_mind/)  
	["The Origins of Common Sense: Modeling human intelligence with Probabilistic Programs and Program Induction"](http://research.microsoft.com/apps/video/default.aspx?id=229021&l=i)  
	["Development of Intelligence: Bayesian Inference"](http://youtube.com/watch?v=icEdI0AIOlU)  
	["Machine vs Human Learning"](http://youtube.com/watch?v=UNYnpO1mkT4)  
	["Cognitive Foundations for Knowledge Representation in AI"](https://drive.google.com/file/d/0B_hicYJxvbiOc1pac0xNZ2JkRFk)  

##

  *(Nando de Freitas)* "For me there are two types of generalisation, which I will refer to as Symbolic and Connectionist generalisation. If we teach a machine to sort sequences of numbers of up to length 10 or 100, we should expect them to sort sequences of length 1000 say. Obviously symbolic approaches have no problem with this form of generalisation, but neural nets do poorly. On the other hand, neural nets are very good at generalising from data (such as images), but symbolic approaches do poorly here. One of the holy grails is to build machines that are capable of both symbolic and connectionist generalisation. Neural Programmer Interpreters is a very early step toward this. NPI can do symbolic operations such as sorting and addition, but it can also plan by taking images as input and it's able to generalise the plans to different images (e.g. in the NPI car example, the cars are test set cars not seen before)."

  *(Pedro Domingos)* "Probabilistic graphical models provide a formal lingua franca for modeling and a common target for efficient inference algorithms. However, many of the most innovative and useful probabilistic models published by the AI, machine learning, and statistics community far outstrip the representational capacity of graphical models and associated inference techniques. Models are communicated using a mix of natural language, pseudo code, and mathematical formulae and solved using special purpose, one-off inference methods. Rather than precise specifications suitable for automatic inference, graphical models typically serve as coarse, high-level descriptions, eliding critical aspects such as fine-grained independence, abstraction and recursion.
  Probabilistic programming languages aim to close this representational gap, unifying general purpose programming with probabilistic modeling; literally, users specify a probabilistic model in its entirety (e.g., by writing code that generates a sample from the joint distribution) and inference follows automatically given the specification. These languages provide the full power of modern programming languages for describing complex distributions, and can enable reuse of libraries of models, support interactive modeling and formal verification, and provide a much-needed abstraction barrier to foster generic, efficient inference in universal model classes."

  *(Andreas Stuhlmueller)* "Probabilistic programs express generative models, i.e., formal descriptions of processes that generate data. To the extent that we can mirror mechanisms “out there in the world” in a formal language, we can pose queries within this language and expect the answer to line up with what happens in the real world. For example, if we can accurately describe how genes give rise to proteins, this helps us in predicting which genetic changes lead to desirable results and which lead to harm.
  Traditionally, Bayesian networks have been used to formalize and reason about such processes. While extremely useful, this formalism is limited in its expressive power compared to programming languages in general. Probabilistic programming languages like Church provide a substrate for computational modeling that brings together Bayesian statistics and Turing-complete programming languages.
  What is the structure of thought? The language of thought hypothesis proposes that thoughts are expressions in a mental language, and that thinking consists of syntactic manipulation of these expressions. The probabilistic language of thought hypothesis suggests that these representations have probabilistic meaning. If we treat concepts as stochastic programs and thinking as approximate Bayesian inference, can we predict human behavior in experimental settings better than using other approaches, e.g., prototype theory? If we learn more about the primitives and composition mechanisms used in the brain to represent abstract concepts, can this inform how we construct tools for reasoning?"



---
### knowledge representation - distributed representations

[distributed representations](https://github.com/brylevkirill/notes/blob/master/Deep%20Learning.md#distributed-representations)



---
### reasoning

 - [neural architectures](#neural-architectures)
 - [natural logic](#natural-logic)
 - [description logic](#description-logic)
 - [formal logic](#formal-logic)
 - [commonsense reasoning](#commonsense-reasoning)

##

#### neural architectures

  "One of the main benefits in using neural networks is that they can be trained to handle very subtle kinds of logic that humans use in casual language that defy axiomatization. Propositional logic, first-order logic, higher-order logic, modal logic, nonmonotonic logic, probabilistic logic, fuzzy logic - none of them seem to quite be adequate; but if you use the right kind of recursive net, you don't even have to specify the logic to get it to make useful deductions, if you have enough training data."


  [distributed representations](https://github.com/brylevkirill/notes/blob/master/Deep%20Learning.md#distributed-representations)  
  [architectures - compute and memory](https://github.com/brylevkirill/notes/blob/master/Deep%20Learning.md#architectures---compute-and-memory)  

  open problems:
  - How to decide what to write and what not to write in the memory?
  - How to represent knowledge to be stored in memories?
  - Types of memory (arrays, stacks, or stored within weights of model), when they should be used, and how can they be learnt?
  - How to do fast retrieval of relevant knowledge from memories when the scale is huge?
  - How to build hierarchical memories, e.g. employing multiscale notions of attention?
  - How to build hierarchical reasoning, e.g. via composition of functions?
  - How to incorporate forgetting/compression of information which is not important?
  - How to properly evaluate reasoning models? Are artificial tasks a good way? Where do they break down and real tasks are needed?
  - Can we draw inspiration from how animal or human memories are stored and used?

##

  "Low-Dimensional Embeddings of Logic" by Rocktaschel, Bosnjak, Singh, Riedel -
	http://techtalks.tv/talks/injecting-logical-background-knowledge-into-embeddings-for-relation-extraction/61526/

  "On Approximate Reasoning Capabilities of Low-Rank Vector Spaces" by Bouchard, Singh, Trouillon -
	https://drive.google.com/file/d/0B_hicYJxvbiObnNYZ0cyMkotUzQ

  "What Can Deep Learning Learn from Symbolic Inference?" by Rocktaschel -
	http://www.bicv.org/?wpdmdl=2309

  - Deep Learning and symbolic rules can be combined efficiently  
    * map logical formulae to differentiable expressions  
    * generalization via learned vector representations  
    * can incorporate explanations via rules leading to more data efficient training  
  - entire reasoning architecture can be end-to-end differentiable  
    * supports multi-hop inference  
    * learns how to prove  
    * induces a latent logic program  
    * trivial to incorporate prior knowledge in form of rules  

##

#### natural logic

  textual entailment: "Recognizing when the meaning of a text snippet is contained in the meaning of a second piece of text. This simple abstraction of an exceedingly complex problem has broad appeal partly because it can be conceived also as a component in other NLP applications. It also avoids commitment to any specific meaning representation and reasoning framework, broadening its appeal within the research community."

  - idea of doing inference over unstructured text
  - weak proof theory over surface linguistic forms
  - can nevertheless model many of the commonsense inferences

  computationally fast during inference:
  - "semantic" parse is just a syntactic parse
  - logical inference is lexical mutation/insertion/deletion

  computationally fast to pre-process:
  - everything is plain text

  captures many common inferences:
  - we make these types of inferences regularly and instantly
  - we expect readers to make these inferences instantly

  introduction by Chris Manning - https://youtu.be/uAk152lIib0?t=25m51s  
  "Open Domain Inference with Natural Logic" by Angeli - https://youtube.com/watch?v=EX1hKxePxkk  

  "Natural Logic: logical inference over text" by Manning -
	http://akbc.ws/2016/slides/manning-akbc16.pdf  
  "Learning Distributed Word Representations for Natural Logic Reasoning" by Bowman, Potts, Manning -
	http://drive.google.com/file/d/0B_hicYJxvbiOeEN5SlBWLUNzLWM  

##

#### description logic

  https://dropbox.com/s/z89eswv4rgkjrlp/OWL.txt
  https://dropbox.com/s/ono4n5yij0y1366/RDF.txt

  "Ontologies and Knowledge Representation" course by Boris Konev (in russian) - https://lektorium.tv/course/22781

  strong assumptions:
  - nothing is ever wrong
  - no contradictions

##

#### formal logic

  "Simply Logical - Intelligent Reasoning by Example" by Peter Flach - https://www.cs.bris.ac.uk/~flach/SL/SL.pdf

  https://intelligence.org/2013/12/21/josef-urban-on-machine-learning-and-automated-reasoning/

  *(Josef Urban)* "Quite reachable is deep automated semantic understanding of most of LaTeX-written mathematical textbooks. This has been blocked by three factors: (i) lack of annotated formal/informal corpora to train such semantic parsing on, (ii) lack of sufficiently large repository of background mathematical knowledge needed for “obvious-knowledge gap-filling”, and (iii) lack of sufficiently strong large-theory ATP that could fill the reasoning gaps using the large repository of background knowledge. One way to try to get them automatically is again through basic computer understanding of LaTeX-written mathematical texts, and learning what high-level concepts like “by analogy” and “using diagonalization” exactly semantically mean in various contexts. This is also related to the ability to reformulate problems and map them to a setting (for current ATPs, the best is purely equational) where the theorem proving becomes more easy. And another related work that needs to be done is “explaining back” the long ATP proofs using an understandable mathematical presentation."

##

#### commonsense reasoning

  "To achieve human-level performance in domains such as natural language processing, vision, and robotics, basic knowledge of the commonsense world - time, space, physical interactions, people, and so on - will be necessary."

  "A well-known example from Terry Winograd is the pair of sentences "The city council refused the demonstrators a permit because they feared violence," vs "... because they advocated violence." To determine that "they" in the first sentence refers to the council if the verb is "feared," but refers to the demonstrators if the verb is "advocated" demands knowledge about the characteristic relations of city councils and demonstrators to violence; no purely linguistic clue suffices."  


  "Commonsense Reasoning and Commonsense Knowledge in Artificial Intelligence" by Davis and Marcus -
	http://cacm.acm.org/magazines/2015/9/191169-commonsense-reasoning-and-commonsense-knowledge-in-artificial-intelligence/fulltext

  "Simulation as an Engine of Physical Scene Understanding" by Battaglia, Hamrick, Tenenbaum - http://www.pnas.org/content/110/45/18327.short

  "Computational Rationality: A Converging Paradigm for Intelligence in Brains, Minds and Machines" by Gershman, Horvitz, Tenenbaum - https://goo.gl/jWaJVf


  "Computational Cognitive Science: Generative Models, Probabilistic Programs and Common Sense" by Tenenbaum - https://youtube.com/watch?v=2WQO9e5Mdj4

  "Learning Physical Intuition of Block Towers by Example" by Lerer, Gross, Fergus - http://arxiv.org/abs/1603.01312



---
### machine comprehension challenges

  - *Allen AI Science Challenge*  
	https://kaggle.com/c/the-allen-ai-science-challenge

	"Moving Beyond the Turing Test with the Allen AI Science Challenge" -
		https://arxiv.org/abs/1604.04315 + http://akbc.ws/2016/slides/etzioni-akbc16.pptx

	first place - https://github.com/Cardal/Kaggle_AllenAIscience  
	second place - https://github.com/bwilbertz/kaggle_allen_ai  
	third place - https://github.com/amsqr/Allen_AI_Kaggle  


  - *Winograd Schema Challenge*  
	http://commonsensereasoning.org/winograd.html

	http://whatsnext.nuance.com/in-the-labs/winograd-schema-challenge-2016-results/  

	"The Winograd Schema Challenge" by Hector Levesque - http://www.cs.toronto.edu/~hector/Papers/winograd.pdf  
	"On our best behaviour" by Hector Levesque - http://www.cs.toronto.edu/~hector/Papers/ijcai-13-paper.pdf  

	set of schemas - pairs of sentences that differ only in one or two words and that contain an ambiguity  
	this ambiguity is resolved in opposite ways in two sentences which requires world knowledge and reasoning  

	as example, "City councilmen refused demonstrators a permit because they [feared | advocated] violence"  
	if the word is "feared" then "they" presumably refers to the city council  
	if the word is "advocated" then "they" presumably refers to the demonstrators  

	solution to each schema is:
	- easily disambiguated by human (ideally, so easily that human does not even notice that there is an ambiguity)
	- not solvable by simple techniques
	- Google-proof (no obvious statistical test over text corpora that will reliably disambiguate these correctly)

	answer to each schema is:
	- a binary choice, in that its performance evaluation is not relative to observer as in Turing test
	- vivid, in that it is obvious to non-experts that a program that fails to get right answers clearly has gaps
	- difficult, in that it is far beyond the current state of the art


  - *Facebook bAbi*  
	http://fb.ai/babi

	- basic factoid qa with single supporting fact
	- factoid qa with two supporting facts
	- factoid qa with three supporting facts
	- two argument relations: subject vs object
	- three argument relations
	- yes/no questions
	- counting
	- lists/sets
	- simple negation
	- indefinite knowledge
	- basic coreference
	- conjunction
	- compound coreference
	- time manipulation
	- basic deduction
	- basic induction
	- positional reasoning
	- reasoning about size
	- path finding
	- reasoning about agent’s motivations


  - *SemEval*  
	http://alt.qcri.org/semeval2014/index.php?id=tasks

	- evaluation of compositional distributional semantic models on full sentences through semantic relatedness and entailment
	- grammar induction for spoken dialogue systems
	- cross-level semantic similarity
	- aspect based sentiment analysis
	- L2 writing assistant
	- supervised semantic parsing of spatial robot commands
	- analysis of clinical text
	- broad-coverage semantic dependency parsing
	- sentiment analysis in Twitter
	- multilingual semantic textual similarity


  - *WikiTableQuestions*  
	http://nlp.stanford.edu/blog/wikitablequestions-a-complex-real-world-question-understanding-dataset/


  - *TAC Knowledge Base Population*  
	http://www.nist.gov/tac/2017/KBP/

	- entity discovery
	- slot filling
	- tri-lingual entity discovery and linking
	- event detection and linking
	- event argument extraction and linking
	- combining or refining independent slot fillings


  - *Visual Genome*  
	http://visualgenome.org


  - *commonsense reasoning*  
	http://commonsensereasoning.org/problem_page.html



---
### machine reading projects


#### Google Knowledge Vault

  "A Web-Scale Approach to Probabilistic Knowledge Fusion" by Kevin Murphy - http://videolectures.net/kdd2014_murphy_knowledge_vault/

  novel facts, trustworthy facts, multimodal knowledge by Kevin Murphy - http://youtube.com/watch?v=i2r5J4XAhsw

  "Constructing and Mining Web-Scale Knowledge Graphs" by Evgeniy Gabrilovich - http://videolectures.net/kdd2014_gabrilovich_bordes_knowledge_graphs/

  "Knowledge Vault and Knowledge-Based Trust" by Xin Luna Dong - http://youtube.com/watch?v=Z6tmDdrBnpU

  "From Data Fusion to Knowledge Fusion" by Xin Luna Dong - http://lunadong.com/talks/fromDFtoKF.pdf

  "Crowdsourcing Knowledge, One Billion Facts at a Time" by Evgeniy Gabrilovich - http://videolectures.net/nipsworkshops2013_gabrilovich_crowdsourcing/

  "A Review of Relational Machine Learning for Knowledge Graphs: From Multi-Relational Link Prediction to Automated Knowledge Graph Construction" by Nickel, Murphy, Tresp, Gabrilovich - http://arxiv.org/abs/1503.00759

##

#### DeepDive

  http://deepdive.stanford.edu  
  http://cs.stanford.edu/people/chrismre/  

  https://blog.acolyer.org/2016/10/07/incremental-knowledge-base-construction-using-deepdive/

  overview by Chris Re -  
	https://vimeo.com/173069166  
	http://youtube.com/watch?v=j1k9lDYCQbA  
	http://videolectures.net/nipsworkshops2013_re_archaeological_texts/  

##

  [showcases](http://deepdive.stanford.edu/doc/showcase/apps.html)  
  [PaleoDB](http://nature.com/news/computers-read-the-fossil-record-1.17868)  

  winner of TAC-KBP 2014 English Slot Filling challenge -  
	http://nlp.cs.rpi.edu/paper/sf2014overview.pdf  
	http://i.stanford.edu/hazy/papers/2014kbp-systemdescription.pdf  

##

  "DeepDive: Design Principles" by Chris Re - http://cs.stanford.edu/people/chrismre/papers/dd.pdf

  "Incremental Knowledge Base Construction Using DeepDive" - http://arxiv.org/abs/1502.00731

  "Probabilistic Inference and Factor Graphs" - http://deepdive.stanford.edu/doc/general/inference.html  
  "Writing inference rules" - http://deepdive.stanford.edu/doc/basics/inference_rules.html  
  "Knowledge Base Construction" - http://deepdive.stanford.edu/doc/general/kbc.html  

##

  "A variety of data-driven problems facing industry, government, and science are macroscopic, in that answering a question requires that one assemble a massive number of disparate signals that are scattered in the natural language text, tables, and even figures of a number of data sources. However, traditional data processing systems are unsuited to these tasks, as they require painful one-off extract-transform-load procedures. DeepDive is a new type of system to extract value from dark data. Like dark matter, dark data is the great mass of data buried in text, tables, figures, and images, which lacks structure and so is essentially unprocessable by existing data systems. DeepDive's most popular use case is to transform the dark data of web pages, pdfs, and other databases into rich SQL-style databases. In turn, these databases can be used to support both SQL-style and predictive analytics. Recently, some DeepDive-based applications have exceeded the quality of human volunteer annotators in both precision and recall for complex scientific articles. The technical core of DeepDive is an engine that combines extraction, integration, and prediction into a single engine with probabilistic inference as its core operation."

  "DeepDive takes a radical view for a data processing system: it views every piece of data as an imperfect observation - which may or may not be correct. It uses these observations and domain knowledge expressed by the user to build a statistical model. One output of this massive model is the most likely database. As aggressive as this approach may sound, it allows for a dramatically simpler user interaction with the system than many of today’s machine learning or extraction systems."

  "Contrary to many traditional machine learning algorithms, which often assume that prior knowledge is exact and make predictions in isolation, DeepDive (Markov Logic Network) performs joint inference: it determines the values of all events at the same time. This allows events to influence each other if they are (directly or indirectly) connected through inference rules. Thus, the uncertainty of one event (John smoking) may influence the uncertainty of another event (John having cancer). As the relationships among events become more complex this model becomes very powerful. For example, one could imagine the event "John smokes" being influenced by whether or not John has friends who smoke. This is particularly useful when dealing with inherently noisy signals, such as human language."

  "Algorithms provide a powerful way to understand an application: if a result looks suspicious, one can trace through the algorithm step-by-step to understand this result. A major challenge is to enable users to understand the results - without explaining how they were computed. DeepDive uses probabilistic inference, which provides a semantically meaningful output independently of how that value is computed. In particular, every fact produced by DeepDive produces an accurate probability value. If DeepDive reports a fact with probability 0.95, then 95% of the facts with that score are correct. In contrast to extraction pipelines that force users to over build individual components in the hope of improving downstream quality, these probabilities take into account all information - allowing the user to focus on quality bottlenecks."

  "One way to improve a KBP system is to integrate domain knowledge. DeepDive supports this operation by allowing the user to integrate constraints and domain knowledge as correlations among random variables. Imagine that the user wants to integrate a simple rule that says “one person is likely to be the spouse of only one person.” For example, given a single entity “Barack Obama,” this rule gives positive preference to the case where only one of (Barack Obama, Michelle Obama) and (Barack Obama, Michelle Williams) is true."



#### Never-Ending Language Learning (NELL)

  http://rtw.ml.cmu.edu/rtw/  
  http://www.cs.cmu.edu/~wcohen/postscript/aaai-2015.pdf  

  - simultaneously learning 500-600 concepts and relations
  - starting point: containment/disjointness relations between concepts, types for relations, and O(10) examples per concept/relation
  - uses 500M web page corpus + live queries

  semi-supervised learning is harder for one concept than for many related concepts together: hard (underconstrained) - much easier (more constrained)

  - suggesting candidate beliefs (using multiple strategies)
  - promoting a set of beliefs consistent with the ontology and each other
  - distantly training the candidate generators from the promoted beliefs

  http://youtube.com/watch?v=psFnHkIjHA0 + https://youtube.com/watch?v=JNNpJ7HAKtk (Mitchell)  
  http://videolectures.net/akbcwekex2012_mitchell_language_learning/ (Mitchell)  
  http://youtube.com/watch?v=51q2IajH94A (Mitchell)  
  http://youtube.com/watch?v=PF6ViL5pcGs (Mitchell)  
  http://videolectures.net/nipsworkshops2013_taludkar_language_learning/ (Talukdar)  
  http://youtube.com/watch?v=--pYaISROqE (Cohen)  



#### AI2 Aristo

  http://allenai.org/aristo.html

  [demo](http://aristo-demo.allenai.org)

  "Unlike entity-centric factoid QA tasks, science questions typically involve general concepts, and answering them requires identifying implicit relationships in the question."

  "Elementary grade science tests are challenging as they test a wide variety of commonsense knowledge that human beings largely take for granted, yet are very difficult for machines. For example, consider a question from a NY Regents 4th Grade science test. Question 1: “When a baby shakes a rattle, it makes a noise. Which form of energy was changed to sound energy?” [Answer: mechanical energy] Science questions are typically quite different from the entity-centric factoid questions extensively studied in the question answering community, e.g., “In which year was Bill Clinton born?” While factoid questions are usually answerable from text search or fact databases, science questions typically require deeper analysis. A full understanding of the above question involves not just parsing and semantic interpretation; it involves adding implicit information to create an overall picture of the “scene” that the text is intended to convey, including facts such as: noise is a kind of sound, the baby is holding the rattle, shaking involves movement, the rattle is making the noise, movement involves mechanical energy, etc. This mental ability to create a scene from partial information is at the heart of natural language understanding, which is essential for answering these kinds of question. It is also very difficult for a machine because it requires substantial world knowledge, and there are often many ways a scene can be elaborated."

  "A first step towards a machine that contains large amounts of knowledge in machine-computable form that can answer questions, explain those answers, and discuss those answers with users. Central to the project is machine reading - semi-automated acquisition of knowledge from natural language texts. We are also integrating semi-formal methods for reasoning with knowledge, such as textual entailment and evidential reasoning, and a robust hybrid architecture that has multiple reasoning modules operating in tandem."

  overview by Peter Clark - https://youtube.com/watch?v=u7n7vKEmfb4



#### IBM Watson

  "The Science Behind an Answer" - http://youtube.com/watch?v=DywO4zksfXw  
  "Building Watson - A Brief Overview of the DeepQA Project" by David Ferucci - http://youtube.com/watch?v=3G2H3DZ8rNc  
  "Inside the Mind of Watson" by Chris Welty - http://youtube.com/watch?v=grDKpicM5y0  
  "Building Watson - A Brief Overview of DeepQA" by Karthik Visweswariah - http://youtube.com/watch?v=_dXNXCv5eo8  

  [papers](https://dropbox.com/sh/udz1kpzzz95xfd6/AADgpBmFsTS1CtkbClfmbyyqa)

##

  Deep Learning graduate student vs IBM Watson team - http://youtu.be/tdLmf8t4oqM?t=31m25s  
  IBM Watson considered a hack compared to Deep Learning - http://spacy.io/blog/dmn.html  

  Jeopardy questions - https://kaggle.com/jeradrose/jeopardy



---
### conferences

  Automated Knowledge Base Construction workshop - http://akbc.ws  
	AKBC 2016 - http://akbc.ws/2016/  
	AKBC 2014 - http://youtube.com/user/NeuralInformationPro/search?query=AKBC  
	AKBC 2012 - http://videolectures.net/akbcwekex2012_montreal/  
	AKBC 2010 - http://videolectures.net/akbc2010_grenoble/  

  StarAI (Statistical and Relational AI) workshop - http://starai.org  

  "Neural Abstract Machines & Program Induction" @ NIPS 2016 - https://uclmr.github.io/nampi/

  "Reasoning, Attention, Memory" workshop @ NIPS 2015 - http://thespermwhale.com/jaseweston/ram/  
  "Cognitive Computation: Integrating Neural and Symbolic Approaches" workshop @ NIPS 2015 - http://neural-symbolic.org/CoCo2015/  

  "Knowledge Representation and Reasoning: Integrating Symbolic and Neural Approaches" workshop - https://sites.google.com/site/krr2015/  

  Learning Semantics workshop - https://sites.google.com/site/learningsemantics2014/  



---
### books and monographies

  Brachman, Levesque - ["Knowledge Representation and Reasoning"](https://goo.gl/JV1JhZ)  
  van Harmelen, Lifschitz, Porter - ["Handbook of Knowledge Representation"](http://dai.fmph.uniba.sk/~sefranek/kri/handbook/)  
  Getoor, Taskar - ["Introduction to Statistical Relational Learning"](http://www.cs.umd.edu/srl-book/)  

  Brenden Lake - ["Towards More Human-Like Concept Learning in Machines: Compositionality, Causality and Learning-to-learn"](http://cims.nyu.edu/~brenden/LakePhDThesis.pdf)  
  Samuel Bowman - ["Modeling Natural Language Semantics in Learned Representations"](https://www.nyu.edu/projects/bowman/bowman2016phd.pdf)  
  Michael Wick - ["Epistemological Databases for Probabilistic Knowledge Base Construction"](http://scholarworks.umass.edu/cgi/viewcontent.cgi?article=1338&context=dissertations_2)  
  Christopher Re - ["Managing Large-scale Probabilistic Databases"](http://pages.cs.wisc.edu/~chrisre/papers/re_thesis.pdf)  
  Matt Gardner - ["Reading and Reasoning with Knowledge Graphs"](http://www.cs.cmu.edu/~mg1/thesis.pdf)  
  Benjamin Roth - ["Effective Distant Supervision for End-To-End Knowledge Base Population Systems"](http://scidok.sulb.uni-saarland.de/volltexte/2015/5983/pdf/thesis_finale_fassung.pdf)  
  Maximilian Nickel - ["Tensor Factorization for Relational Learning"](http://edoc.ub.uni-muenchen.de/16056/1/Nickel_Maximilian.pdf)  
  Anthony Fader - ["Open Question Answering"](https://digital.lib.washington.edu/researchworks/bitstream/handle/1773/26336/Fader_washington_0250E_13164.pdf)  
  Xuchen Yao - ["Feature-Driven Question Answering with Natural Language Alignment"](https://www.cs.jhu.edu/~xuchen/paper/xuchenyao-phd-dissertation.pdf)  



---
### interesting papers


  - [knowledge representation and reasoning](https://dropbox.com/sh/9ytscy4pwegbvhb/AACtB7tQGj-vigo0yExfciu0a)
  - [information extraction and integration](https://dropbox.com/sh/jmkl4mhajjghjxk/AABfAImA69Kzxx3b0IhCGouMa)
  - [reasoning](https://dropbox.com/sh/ju4oi0221zo3ql7/AAC8SscYIxR5uk3CVhQXpkuda)
  - [Resource Description Framework](https://dropbox.com/sh/c427b94xex62a40/AABii9_MRHrCZPGJ_Adx_b3Ma)


[recent interesting papers](https://github.com/brylevkirill/notes/blob/master/recent%20papers.txt)


interesting papers (see below):
  - [knowledge bases](#interesting-papers---knowledge-bases)
  - [knowledge bases with discrete representations](#interesting-papers---knowledge-bases-with-discrete-representations)
  - [knowledge bases with continuous representations](#interesting-papers---knowledge-bases-with-continuous-representations)
  - [continuous representations of text](#interesting-papers---continuous-representations-of-text)
  - [question answering over knowledge bases](#interesting-papers---question-answering-over-knowledge-bases)
  - [question answering over texts](#interesting-papers---question-answering-over-texts)
  - [reasoning](#interesting-papers---reasoning)
  - [information extraction and integration](#interesting-papers---information-extraction-and-integration)
  - [multimodal knowledge representation](#interesting-papers---multimodal-knowledge-representation)



---
### interesting papers - knowledge bases

#### Dong, Gabrilovich, Heitz, Horn, Lao, Murphy, Strohmann, Sun, Zhang - ["Knowledge Vault: A Web-Scale Approach to Probabilistic Knowledge Fusion"](https://www.cs.cmu.edu/~nlao/publication/2014.kdd.pdf) (Google Knowledge Vault)
>	"Recent years have witnessed a proliferation of large-scale knowledge bases, including Wikipedia, Freebase, YAGO, Microsoft's Satori, and Google's Knowledge Graph. To increase the scale even further, we need to explore automatic methods for constructing knowledge bases. Previous approaches have primarily focused on text-based extraction, which can be very noisy. Here we introduce Knowledge Vault, a Web-scale probabilistic knowledge base that combines extractions from Web content (obtained via analysis of text, tabular data, page structure, and human annotations) with prior knowledge derived from existing knowledge repositories. We employ supervised machine learning methods for fusing these distinct information sources. The Knowledge Vault is substantially bigger than any previously published structured knowledge repository, and features a probabilistic inference system that computes calibrated probabilities of fact correctness. We report the results of multiple studies that explore the relative utility of the relative utility of the different information sources and extraction methods."

  - http://videolectures.net/kdd2014_murphy_knowledge_vault/ (Murphy)
  - http://videolectures.net/kdd2014_gabrilovich_bordes_knowledge_graphs/ (Gabrilovich)
  - http://cikm2013.org/slides/kevin.pdf


#### Mitchell, Cohen, Hruschka, Talukdar, Betteridge, Carlson, Dalvi, Gardner, Kisiel, Krishnamurthy, Lao, Mazaitis, Mohamed, Nakashole, Platanios, Ritter, Samadi, Settles, Wang, Wijaya, Gupta, Chen, Saparov, Greaves, Welling - ["Never-Ending Learning"](http://www.cs.cmu.edu/~wcohen/postscript/aaai-2015.pdf) (NELL knowledge base)
>	"Whereas people learn many different types of knowledge from diverse experiences over many years, most current machine learning systems acquire just a single function or data model from just a single data set. We propose a never-ending learning paradigm for machine learning, to better reflect the more ambitious and encompassing type of learning performed by humans. As a case study, we describe the Never-Ending Language Learner, which achieves some of the desired properties of a never-ending learner, and we discuss lessons learned. NELL has been learning to read the web 24 hours/day since January 2010, and so far has acquired a knowledge base with over 80 million confidence-weighted beliefs (e.g., servedWith(tea, biscuits)), while learning continually to improve its reading competence over time. NELL has also learned to reason over its knowledge base to infer new beliefs from old ones, and is now beginning to extend its ontology by synthesizing new relational predicates."

  - http://youtube.com/watch?v=PF6ViL5pcGs (Mitchell)
  - http://youtube.com/watch?v=--pYaISROqE (Cohen)
  - http://videolectures.net/nipsworkshops2013_taludkar_language_learning/ (Talukdar)


#### Re, Sadeghian, Shan, Shin, Wang, Wu, Zhang - ["Feature Engineering for Knowledge Base Construction"](http://arxiv.org/abs/1407.6439) (DeepDive knowledge base)
>	"Knowledge base construction is the process of populating a knowledge base, i.e., a relational database together with inference rules, with information extracted from documents and structured sources. KBC blurs the distinction between two traditional database problems, information extraction and information integration. For the last several years, our group has been building knowledge bases with scientific collaborators. Using our approach, we have built knowledge bases that have comparable and sometimes better quality than those constructed by human volunteers. In contrast to these knowledge bases, which took experts a decade or more human years to construct, many of our projects are constructed by a single graduate student. Our approach to KBC is based on joint probabilistic inference and learning, but we do not see inference as either a panacea or a magic bullet: inference is a tool that allows us to be systematic in how we construct, debug, and improve the quality of such systems. In addition, inference allows us to construct these systems in a more loosely coupled way than traditional approaches. To support this idea, we have built the DeepDive system, which has the design goal of letting the user "think about features---not algorithms." We think of DeepDive as declarative in that one specifies what they want but not how to get it. We describe our approach with a focus on feature engineering, which we argue is an understudied problem relative to its importance to end-to-end quality."


#### Wu, Zhang, Wang, Re - ["Incremental Knowledge Base Construction Using DeepDive"](http://arxiv.org/abs/1502.00731) (DeepDive knowledge base)
>	"Populating a database with unstructured information is a long-standing problem in industry and research that encompasses problems of extraction, cleaning, and integration. A recent name used to characterize this problem is Knowledge Base Construction. In this work, we describe DeepDive, a system that combines database and machine learning ideas to help develop KBC systems, and we present techniques to make the KBC process more efficient. We observe that the KBC process is iterative, and we develop techniques to incrementally produce inference results for KBC systems. We propose two methods for incremental inference, based respectively on sampling and variational techniques. We also study the tradeoff space of these methods and develop a simple rule-based optimizer. DeepDive includes all of these contributions, and we evaluate DeepDive on five KBC systems, showing that it can speed up KBC inference tasks by up to two orders of magnitude with negligible impact on quality."

  - http://youtube.com/watch?v=j1k9lDYCQbA (Re)


#### Mahdisoltani, Biega, Suchanek - ["YAGO3: A Knowledge Base from Multilingual Wikipedias"](http://suchanek.name/work/publications/cidr2015.pdf) (Yago knowledge base)
>	"We present YAGO3, an extension of the YAGO knowledge base that combines the information from the Wikipedias in multiple languages. Our technique fuses the multilingual information with the English WordNet to build one coherent knowledge base. We make use of the categories, the infoboxes, and Wikidata, and learn the meaning of infobox attributes across languages. We run our method on 10 different languages, and achieve a precision of 95%-100% in the attribute mapping. Our technique enlarges YAGO by 1m new entities and 7m new facts."


#### Clark, Balasubramanian, Bhakthavatsalam, Humphreys, Kinkead, Sabharwal, Tafjord - ["Automatic Construction of Inference-Supporting Knowledge Bases"](http://akbc.ws/2014/submissions/akbc2014_submission_32.pdf) (AI2 knowledge base)
>	"While there has been tremendous progress in automatic database population in recent years, most of human knowledge does not naturally fit into a database form. For example, knowledge that "metal objects can conduct electricity" or "animals grow fur to help them stay warm" requires a substantially different approach to both acquisition and representation. This kind of knowledge is important because it can support inference e.g., (with some associated confidence) if an object is made of metal then it can conduct electricity; if an animal grows fur then it will stay warm. If we want our AI systems to understand and reason about the world, then acquisition of this kind of inferential knowledge is essential. In this paper, we describe our work on automatically constructing an inferential knowledge base, and applying it to a question-answering task. Rather than trying to induce rules from examples, or enter them by hand, our goal is to acquire much of this knowledge directly from text. Our premise is that much inferential knowledge is written down explicitly, in particular in textbooks, and can be extracted with reasonable reliability. We describe several challenges that this approach poses, and innovative, partial solutions that we have developed."

  - http://youtube.com/watch?v=eyjpLPjhSPU (Clark)
  - https://drive.google.com/file/d/0B_hicYJxvbiOd3pwZTNnaDRHdFU



---
### interesting papers - knowledge bases with discrete representations

#### Nickel, Murphy, Tresp, Gabrilovich - ["A Review of Relational Machine Learning for Knowledge Graphs: From Multi-Relational Link Prediction to Automated Knowledge Graph Construction"](http://arxiv.org/abs/1503.00759) (Google Knowledge Vault)
>	"Relational machine learning studies methods for the statistical analysis of relational, or graph-structured, data. In this paper, we provide a review of how such statistical models can be "trained" on large knowledge graphs, and then used to predict new facts about the world (which is equivalent to predicting new edges in the graph). In particular, we discuss two different kinds of statistical relational models, both of which can scale to massive datasets. The first is based on tensor factorization methods and related latent variable models. The second is based on mining observable patterns in the graph. We also show how to combine these latent and observable models to get improved modeling power at decreased computational cost. Finally, we discuss how such statistical models of graphs can be combined with text-based information extraction methods for automatically constructing knowledge graphs from the Web. In particular, we discuss Google's Knowledge Vault project."


#### Dalvi, Cohen, Callan - ["Classifying Entities into an Incomplete Ontology"](https://www.cs.cmu.edu/~bbd/bbd_akbc13_submitted.pdf) (automated ontology construction used in NELL)
>	"Exponential growth of unlabeled web-scale datasets, and class hierarchies to represent them, has given rise to new challenges for hierarchical classification. It is costly and time consuming to create a complete ontology of classes to represent entities on the Web. Hence, there is a need for techniques that can do hierarchical classification of entities into incomplete ontologies. In this paper we present Hierarchical Exploratory EM algorithm (an extension of the Exploratory EM algorithm) that takes a seed class hierarchy and seed class instances as input. Our method classifies relevant entities into some of the classes from the seed hierarchy and on its way adds newly discovered classes into the hierarchy. Experiments with subsets of the NELL ontology and text datasets derived from the ClueWeb09 corpus show that our Hierarchical Exploratory EM approach improves seed class F1 by up to 21% when compared to its semi-supervised counterpart."


#### Lao, Mitchell, Cohen - ["Random Walk Inference and Learning in A Large Scale Knowledge Base"](http://www.cs.cmu.edu/~tom/pubs/lao-emnlp11.pdf) (PRA inference method used in Google Knowledge Vault and NELL)
>	"We consider the problem of performing learning and inference in a large scale knowledge base containing imperfect knowledge with incomplete coverage. We show that a soft inference procedure based on a combination of constrained, weighted, random walks through the knowledge base graph can be used to reliably infer new beliefs for the knowledge base. More specifically, we show that the system can learn to infer different target relations by tuning the weights associated with random walks that follow different paths through the graph, using a version of the Path Ranking Algorithm. We apply this approach to a knowledge base of approximately 500,000 beliefs extracted imperfectly from the web by NELL, a never-ending language learner. This new system improves significantly over NELL’s earlier Horn-clause learning and inference method: it obtains nearly double the precision at rank 100, and the new learning method is also applicable to many more inference tasks."

  - http://cs.cmu.edu/~nlao/publication/2012/defense.pdf
  - https://github.com/matt-gardner/pra


#### Lao, Subramanya, Pereira, Cohen - ["Reading The Web with Learned Syntactic-Semantic Inference Rules"](http://www.cs.cmu.edu/~nlao/publication/2012/2012.emnlp.paper.pdf) (PRA inference method used in NELL)
>	"We study how to extend a large knowledge base (Freebase) by reading relational information from a large Web text corpus. Previous studies on extracting relational knowledge from text show the potential of syntactic patterns for extraction, but they do not exploit background knowledge of other relations in the knowledge base. We describe a distributed, Web-scale implementation of a path-constrained random walk model that learns syntactic-semantic inference rules for binary relations from a graph representation of the parsed text and the knowledge base. Experiments show significant accuracy improvements in binary relation prediction over methods that consider only text, or only the existing knowledge base."


#### Gardner, Talukdar, Kisiel, Mitchell - ["Improving Learning and Inference in a Large Knowledge Base Using Latent Syntactic Cues"](http://talukdar.net/papers/latent_pra_emnlp13.pdf) (PRA inference method used in NELL)
>	"Automatically constructed Knowledge Bases are often incomplete and there is a genuine need to improve their coverage. Path Ranking Algorithm is a recently proposed method which aims to improve KB coverage by performing inference directly over the KB graph. For the first time, we demonstrate that addition of edges labeled with latent features mined from a large dependency parsed corpus of 500 million Web documents can significantly outperform previous PRA based approaches on the KB inference task. We present extensive experimental results validating this finding. The resources presented in this paper are publicly available."


#### Gardner, Mitchell - ["Efficient and Expressive Knowledge Base Completion Using Subgraph Feature Extraction"](https://www.cs.cmu.edu/~mg1/paper.pdf) (PRA inference method used in NELL)
>	"We explore some of the practicalities of using random walk inference methods, such as the Path Ranking Algorithm, for the task of knowledge base completion. We show that the random walk probabilities computed (at great expense) by PRA provide no discernible benefit to performance on this task, and so they can safely be dropped. This result allows us to define a simpler algorithm for generating feature matrices from graphs, which we call subgraph feature extraction. In addition to being conceptually simpler than PRA, SFE is much more efficient, reducing computation by an order of magnitude, and more expressive, allowing for much richer features than just paths between two nodes in a graph. We show experimentally that this technique gives substantially better performance than PRA and its variants, improving mean average precision from .432 to .528 on a knowledge base completion task using the NELL knowledge base."

>	"We have explored several practical issues that arise when using the path ranking algorithm for knowledge base completion. An analysis of several of these issues led us to propose a simpler algorithm, which we called subgraph feature extraction, which characterizes the subgraph around node pairs and extracts features from that subgraph. SFE is both significantly faster and performs better than PRA on this task. We showed experimentally that we can reduce running time by an order of magnitude, while at the same time improving mean average precision from .432 to .528 and mean reciprocal rank from .850 to .933. This thus constitutes the best published results for knowledge base completion on NELL data."

  - http://www.cs.cmu.edu/~mg1/thesis.pdf - "Reading and Reasoning with Knowledge Graphs" thesis by Gardner
>	"As a final point of future work, we note that we have taken PRA, an elegant model that has strong ties to logical inference, and reduced it with SFE to feature extraction over graphs. It seems clear experimentally that this is a significant improvement, but somehow doing feature engineering over graphs is not incredibly satisfying. We introduced a few kinds of features with SFE that we thought might work well, but there are many, many more kinds of features we could have experimented with (e.g., counts of paths found, path unigrams, path trigrams, conjunctions of simple paths, etc.). How should we wade our way through this mess of feature engineering? This is not a task we eagerly anticipate. One possible way around this is to turn to deep learning, whose promise has always been to push the task of feature engineering to the neural network. Some initial work on creating embeddings of graphs has been done (Bruna et al., 2013), but that work dealt with unlabeled graphs and would need significant modification to work in this setting. The recursive neural network of Neelakantan et al. (2015) is also a step in the right direction, though the spectral networks of Bruna et al. seem closer to the necessary network structure here."

  - http://youtube.com/watch?v=dp2waL7OLbI (Gardner)


#### Wick, McCallum, Miklau - ["Scalable Probabilistic Databases with Factor Graphs and MCMC"](http://people.cs.umass.edu/~mwick/MikeWeb/Publications_files/wick10scalable.pdf) (inference method used in Epistemological database)
>	"Incorporating probabilities into the semantics of incomplete databases has posed many challenges, forcing systems to sacrifice modeling power, scalability, or treatment of relational algebra operators. We propose an alternative approach where the underlying relational database always represents a single world, and an external factor graph encodes a distribution over possible worlds; Markov chain Monte Carlo inference is then used to recover this uncertainty to a desired level of fidelity. Our approach allows the efficient evaluation of arbitrary queries over probabilistic databases with arbitrary dependencies expressed by graphical models with structure that changes during inference. MCMC sampling provides efficiency by hypothesizing modifications to possible worlds rather than generating entire worlds from scratch. Queries are then run over the portions of the world that change, avoiding the onerous cost of running full queries over each sampled world. A significant innovation of this work is the connection between MCMC sampling and materialized view maintenance techniques: we find empirically that using view maintenance techniques is several orders of magnitude faster than naively querying each sampled world. We also demonstrate our system’s ability to answer relational queries with aggregation, and demonstrate additional scalability through the use of parallelization on a real-world complex model of information extraction. This framework is sufficiently expressive to support probabilistic inference not only for answering queries, but also for inferring missing database content from raw evidence."


#### Domingos, Kok, Lowd, Poon, Richardson, Singla - ["Markov Logic"](http://homes.cs.washington.edu/~pedrod/papers/pilp.pdf) (MLN probabilistic database)
>	"Most real-world machine learning problems have both statistical and relational aspects. Thus learners need representations that combine probability and relational logic. Markov logic accomplishes this by attaching weights to first-order formulas and viewing them as templates for features of Markov networks. Inference algorithms for Markov logic draw on ideas from satisfiability, Markov chain Monte Carlo and knowledge-based model construction. Learning algorithms are based on the conjugate gradient algorithm, pseudo-likelihood and inductive logic programming. Markov logic has been successfully applied to problems in entity resolution, link prediction, information extraction and others, and is the basis of the open-source Alchemy system."


#### Niu, Re, Doan, Shavlik - ["Tuffy: Scaling up Statistical Inference in Markov Logic Networks using an RDBMS"](http://cs.stanford.edu/people/chrismre/papers/tuffy.pdf) (MLN probabilistic database)
>	"Over the past few years, Markov Logic Networks have emerged as a powerful AI framework that combines statistical and logical reasoning. It has been applied to a wide range of data management problems, such as information extraction, ontology matching, and text mining, and has become a core technology underlying several major AI projects. Because of its growing popularity, MLNs are part of several research programs around the world. None of these implementations, however, scale to large MLN data sets. This lack of scalability is now a key bottleneck that prevents the widespread application of MLNs to real-world data management problems. In this paper we consider how to leverage RDBMSes to develop a solution to this problem. We consider Alchemy, the state-of-the-art MLN implementation currently in wide use. We first develop bTuffy, a system that implements Alchemy in an RDBMS. We show that bTuffy already scales to much larger datasets than Alchemy, but suffers from a sequential processing problem (inherent in Alchemy). We then propose cTuffy that makes better use of the RDBMS’s set-at-a-time processing ability. We show that this produces dramatic benefits: on all four benchmarks cTuffy dominates both Alchemy and bTuffy. Moreover, on the complex entity resolution benchmark cTuffy finds a solution in minutes, while Alchemy spends hours unsuccessfully. We summarize the lessons we learnt, on how we can design AI algorithms to take advantage of RDBMSes, and extend RDBMSes to work better for AI algorithms."

>	"Motivated by a staggeringly large set of applications, we propose Tuffy that pushes MLN inference inside an RDBMS. We find that MLN inference uses many “relational-like” operations and that these operations are a substantial bottleneck in MLN inference. To alleviate this bottleneck, we propose cTuffy, which in addition to using an RDBMS modified the state-of-the-art search algorithms to be set-ata-time. We believe that we are the first to push search algorithms inside an RDBMS, and that our prototype cTuffy demonstrates that this is a promising new direction for database research to support increasingly sophisticated statistical models. As future work, we plan to study whether main memory databases can be used in conjunction with RDBMSes to provide more efficient implementation of search procedures."


#### Domingos, Webb - ["A Tractable First-Order Probabilistic Logic"](http://homes.cs.washington.edu/~pedrod/papers/aaai12.pdf) (MLN probabilistic database)
>	"Tractable subsets of first-order logic are a central topic in AI research. Several of these formalisms have been used as the basis for first-order probabilistic languages. However, these are intractable, losing the original motivation. Here we propose the first non-trivially tractable first-order probabilistic language. It is a subset of Markov logic, and uses probabilistic class and part hierarchies to control complexity. We call it Tractable Markov Logic. We show that TML knowledge bases allow for efficient inference even when the corresponding graphical models have very high treewidth. We also show how probabilistic inheritance, default reasoning, and other inference patterns can be carried out in TML. TML opens up the prospect of efficient large-scale first-order probabilistic inference."

  - http://youtube.com/watch?v=6ZJzfRdCZjc (Domingos)


#### Niepert, Domingos - ["Tractable Probabilistic Knowledge Bases: Wikipedia and Beyond"](http://www.aaai.org/ocs/index.php/WS/AAAIW14/paper/download/8722/8239) (MLN probabilistic database)
>	"Building large-scale knowledge bases from a variety of data sources is a longstanding goal of AI research. However, existing approaches either ignore the uncertainty inherent to knowledge extracted from text, the web, and other sources, or lack a consistent probabilistic semantics with tractable inference. To address this problem, we present a framework for tractable probabilistic knowledge bases. TPKBs consist of a hierarchy of classes of objects and a hierarchy of classes of object pairs such that attributes and relations are independent conditioned on those classes. These characteristics facilitate both tractable probabilistic reasoning and tractable maximum-likelihood parameter learning. TPKBs feature a rich query language that allows one to express and infer complex relationships between classes, relations, objects, and their attributes. The queries are translated to sequences of operations in a relational database facilitating query execution times in the sub-second range. We demonstrate the power of TPKBs by leveraging large data sets extracted from Wikipedia to learn their structure and parameters. The resulting TPKB models a distribution over millions of objects and billions of parameters. We apply the TPKB to entity resolution and object linking problems and show that the TPKB can accurately align large knowledge bases and integrate triples from open IE projects."

  - http://youtube.com/watch?v=6ZJzfRdCZjc (Domingos)
  - http://alchemy.cs.washington.edu/lite/


#### Niepert, Domingos - ["Learning and Inference in Tractable Probabilistic Knowledge Bases"](http://homes.cs.washington.edu/~pedrod/papers/uai15.pdf) (MLN probabilistic database)
>	"Building efficient large-scale knowledge bases is a longstanding goal of AI. KBs need to be first-order to be sufficiently expressive, and probabilistic to handle uncertainty, but these lead to intractable inference. Recently, tractable Markov logic was proposed as a nontrivial tractable first-order probabilistic representation. This paper describes the first inference and learning algorithms for TML, and its application to real-world problems. Inference takes time per query sublinear in the size of the KB, and supports very large KBs via parallelization and a disk-based implementation using a relational database engine. Query answering is fast enough for interactive and real-time use. We show that, despite the data being non-i.i.d. in general, maximum likelihood parameters for TML knowledge bases can be computed in closed form. We use our algorithms to build a very large tractable probabilistic KB from numerous heterogeneous data sets. The KB includes millions of objects and billions of parameters. Our experiments show that the learned KB outperforms existing specialized approaches on challenging tasks in information extraction and integration."

>	"We presented a novel inference algorithm for TPKBs that is disk-based, parallel, and sublinear. We also derived closed-form maximum likelihood estimates for TPKB parameters. We used these results to learn a large TPKB from multiple data sources and applied it to information extraction and integration problems. The TPKB outperformed existing algorithms in accuracy and efficiency. Future work will be concerned with more sophisticated smoothing approaches, the comparison of different learning strategies, and the problem of structure learning. We also plan to apply TPKBs to a wide range of problems that benefit from tractable probabilistic knowledge representations."

  - http://youtube.com/watch?v=6ZJzfRdCZjc (Domingos)
  - http://alchemy.cs.washington.edu/lite/


#### Pujara, Getoor - ["Building Dynamic Knowledge Graphs"](http://linqs.cs.umd.edu/basilic/web/Publications/2014/pujara:akbc14/pujara_akbc14.pdf) (PSL probabilistic database)
>	"One of the fundamental challenges in constructing knowledge bases is that the knowledge we seek to capture comes from an uncertain and changing world. Constructing a KB necessitates dealing with a continual flow of evidence that requires updating and revising the KB. A key question for the AKBC community is how to construct and update KBs using a steadily growing stream of noisy extractions from large text corpora, like the Web. In this vision paper, we (1) formalize the problem of building a dynamic knowledge graph, (2) define a probabilistic model for using new evidence to update the knowledge graph, and (3) present an efficient algorithm for knowledge graph construction on streaming extractions."


#### Pujara, Miao, Getoor, Cohen - ["Large-Scale Knowledge Graph Identification using PSL"](http://linqs.cs.umd.edu/basilic/web/Publications/2013/pujara:slg13/pujara_slg13.pdf) (PSL probabilistic database)
>	"Knowledge graphs present a Big Data problem: reasoning collectively about millions of interrelatd facts. We formulate the problem of knowledge graph identification, jointly inferring a knowledge graph from the noisy output of an information extraction system through a combined process of determining co-referent entities, predicting relational links, collectively classifying entity labels, and enforcing ontological constraints. Using PSL, we illustrate the scalability benefits of our approach on a large-scale dataset from NELL, while producing high-precision results. Our method provides a substantial increase in F1 score while also improving AUC and scales linearly with the number of ground rules. In practice, we show that on a NELL dataset our method can infer a full knowledge graph in just two hours or make predictions on a known query set in a matter of seconds."

>	"Large-scale information processing systems are able to extract massive collections of interrelated facts, but unfortunately transforming these candidate facts into useful knowledge is a formidable challenge. In this paper, we show how uncertain extractions about entities and their relations can be transformed into a knowledge graph. The extractions form an extraction graph and we refer to the task of removing 
noise, inferring missing information, and determining which candidate facts should be included into a knowledge graph as knowledge graph identification. In order to perform this task, we must reason jointly about candidate facts and their associated extraction confidences, identify coreferent entities, and incorporate ontological constraints. Our proposed approach uses Probabilistic Soft Logic, a recently introduced probabilistic modeling framework which easily scales to millions of facts. We demonstrate the power of our method on a synthetic Linked Data corpus derived from the MusicBrainz music community and a real-world set of extractions from the NELL project containing over 1M extractions and 70K ontological relations. We show that compared to existing methods, our approach is able to achieve improved AUC and F1 with significantly lower running time."

  - http://youtube.com/watch?v=z_VzaNy36xE (Pujara)
  - http://youtube.com/watch?v=--pYaISROqE (Cohen)


#### Wang, Mazaitis, Lao, Mitchell, Cohen - ["Efficient Inference and Learning in a Large Knowledge Base: Reasoning with Extracted Information using a Locally Groundable First-Order Probabilistic Logic"](http://arxiv.org/abs/1404.3301) (ProPPR probabilistic database)
>	"One important challenge for probabilistic logics is reasoning with very large knowledge bases of imperfect information, such as those produced by modern web-scale information extraction systems. One scalability problem shared by many probabilistic logics is that answering queries involves “grounding” the query - i.e., mapping it to a propositional representation - and the size of a “grounding” grows with database size. To address this bottleneck, we present a first-order probabilistic language called ProPPR in which that approximate “local groundings” can be constructed in time independent of database size. Technically, ProPPR is an extension to Stochastic Logic Programs that is biased towards short derivations; it is also closely related to an earlier relational learning algorithm called the Path Ranking Algorithm. We show that the problem of constructing proofs for this logic is related to computation of Personalized PageRank on a linearized version of the proof space, and using on this connection, we develop a proveably-correct approximate grounding scheme, based on the PageRank-Nibble algorithm. Building on this, we develop a fast and easily-parallelized weight-learning algorithm for ProPPR. In experiments, we show that learning for ProPPR is orders magnitude faster than learning for Markov Logic Networks; that allowing mutual recursion (joint learning) in KB inference leads to improvements in performance; and that ProPPR can learn weights for a mutually recursive program with hundreds of clauses, which define scores of interrelated predicates, over a KB containing one million entities."

  - http://youtu.be/--pYaISROqE?t=12m35s (Cohen)
  - http://www.cs.cmu.edu/afs/cs/Web/People/wcohen/nlu-2014.ppt
  - https://www.cs.cmu.edu/afs/cs.cmu.edu/Web/People/yww/papers/starAI.pdf
  - https://drive.google.com/file/d/0B_hicYJxvbiOc05xNEhvdVVSQWc/
  - https://github.com/TeamCohen/ProPPR


#### Wang, Mazaitis, Cohen - ["Structure Learning via Parameter Learning"](https://www.cs.cmu.edu/~wcohen/postscript/cikm-2014-structure.pdf) (ProPPR probabilistic database)
>	"A key challenge in information and knowledge management is to automatically discover the underlying structures and patterns from large collections of extracted information. This paper presents a novel structure-learning method for a new, scalable probabilistic logic called ProPPR. Our approach builds on the recent success of meta-interpretive learning methods in Inductive Logic Programming, and we further extends it to a framework that enables robust and efficient structure learning of logic programs on graphs: using an abductive second-order probabilistic logic, we show how first-order theories can be automatically generated via parameter learning. To learn better theories, we then propose an iterated structural gradient approach that incrementally refines the hypothesized space of learned first-order structures. In experiments, we show that the proposed method further improves the results, outperforming competitive baselines such as Markov Logic Networks and FOIL on multiple datasets with various settings; and that the proposed approach can learn structures in a large knowledge base in a tractable fashion."

  - http://youtu.be/--pYaISROqE?t=21m35s (Cohen)



---
### interesting papers - knowledge bases with continuous representations

#### Sutskever, Salakhutdinov, Tenenbaum - ["Modelling Relational Data using Bayesian Clustered Tensor Factorization"](http://www.cs.toronto.edu/~rsalakhu/papers/pmfcrp.pdf) (probabilistic model over distributed representations)
>	"We consider the problem of learning probabilistic models for complex relational structures between various types of objects. A model can help us “understand” a dataset of relational facts in at least two ways, by finding interpretable structure in the data, and by supporting predictions, or inferences about whether particular unobserved relations are likely to be true. Often there is a tradeoff between these two aims: cluster-based models yield more easily interpretable representations, while factorization-based approaches have given better predictive performance on large data sets. We introduce the Bayesian Clustered Tensor Factorization model, which embeds a factorized representation of relations in a nonparametric Bayesian clustering framework. Inference is fully Bayesian but scales well to large data sets. The model simultaneously discovers interpretable clusters and yields predictive performance that matches or beats previous probabilistic models for relational data."


#### Bordes, Weston, Collobert, Bengio - ["Learning Structured Embeddings of Knowledge Bases"](http://ronan.collobert.com/pub/matos/2011_knowbases_aaai.pdf) (Distance model)
>	"Many Knowledge Bases are now readily available and encompass colossal quantities of information thanks to either a long-term funding effort (e.g. WordNet, OpenCyc) or a collaborative process (e.g. Freebase, DBpedia). However, each of them is based on a different rigorous symbolic framework which makes it hard to use their data in other systems. It is unfortunate because such rich structured knowledge might lead to a huge leap forward in many other areas of AI like natural language processing (word-sense disambiguation, natural language understanding, ...), vision (scene classification, image semantic annotation, ...) or collaborative filtering. In this paper, we present a learning process based on an innovative neural network architecture designed to embed any of these symbolic representations into a more flexible continuous vector space in which the original knowledge is kept and enhanced. These learnt embeddings would allow data from any KB to be easily used in recent machine learning methods for prediction and information retrieval. We illustrate our method on WordNet and Freebase and also present a way to adapt it to knowledge extraction from raw text."


#### Jenatton, Roux, Bordes, Obozinski - ["A Latent Factor Model for Highly Multi-Relational Data"](http://papers.nips.cc/paper/4744-a-latent-factor-model-for-highly-multi-relational-data.pdf) (Bilinear model)
>	"Many data such as social networks, movie preferences or knowledge bases are multi-relational, in that they describe multiple relations between entities. While there is a large body of work focused on modeling these data, modeling these multiple types of relations jointly remains challenging. Further, existing approaches tend to breakdown when the number of these types grows. In this paper, we propose a method for modeling large multi-relational datasets, with possibly thousands of relations. Our model is based on a bilinear structure, which captures various orders of interaction of the data, and also shares sparse latent factors across different relations. We illustrate the performance of our approach on standard tensor-factorization datasets where we attain, or outperform, state-of-the-art results. Finally, a NLP application demonstrates our scalability and the ability of our model to learn efficient and semantically meaningful verb representations."


#### Socher, Chen, Manning, Ng - ["Reasoning With Neural Tensor Networks for Knowledge Base Completion"](http://nlp.stanford.edu/pubs/SocherChenManningNg_NIPS2013.pdf) (NTN model)
>	"Knowledge bases are an important resource for question answering and other tasks but often suffer from incompleteness and lack of ability to reason over their discrete entities and relationships. In this paper we introduce an expressive neural tensor network suitable for reasoning over relationships between two entities. Previous work represented entities as either discrete atomic units or with a single entity vector representation. We show that performance can be improved when entities are represented as an average of their constituting word vectors. This allows sharing of statistical strength between, for instance, facts involving the “Sumatran tiger” and “Bengal tiger.” Lastly, we demonstrate that all models improve when these word vectors are initialized with vectors learned from unsupervised large corpora. We assess the model by considering the problem of predicting additional true relations between entities given a subset of the knowledge base. Our model outperforms previous models and can classify unseen relationships in WordNet and FreeBase with an accuracy of 86.2% and 90.0%, respectively."


#### Bordes, Usunier, Garcia-Duran, Weston, Yakhnenko - ["Translating Embeddings for Modeling Multi-relational Data"](http://papers.nips.cc/paper/5071-translating-embeddings-for-modeling-multi-relational-data) (TransE model)
>	"We consider the problem of embedding entities and relationships of multi-relational data in low-dimensional vector spaces. Our objective is to propose a canonical model which is easy to train, contains a reduced number of parameters and can scale up to very large databases. Hence, we propose, TransE, a method which models relationships by interpreting them as translations operating on the low-dimensional embeddings of the entities. Despite its simplicity, this assumption proves to be powerful since extensive experiments show that TransE significantly outperforms state-of-the-art methods in link prediction on two knowledge bases. Besides, it can be successfully trained on a large scale data set with 1M entities, 25k relationships and more than 17M training samples."

  - http://youtube.com/watch?v=YkVvOBylV5k + http://akbc.ws/2014/slides/weston-nips-akbc.pdf (Weston)
  - https://github.com/glorotxa/SME


#### Yang, Yih, He, Gao, Deng - ["Embedding Entities and Relations for Learning and Inference in Knowledge Bases"](http://arxiv.org/abs/1412.6575) (DistMult model)
>	"We consider learning representations of entities and relations in KBs using the neural-embedding approach. We show that most existing models, including NTN and TransE, can be generalized under a unified learning framework, where entities are low-dimensional vectors learned from a neural network and relations are bilinear and/or linear mapping functions. Under this framework, we compare a variety of embedding models on the link prediction task. We show that a simple bilinear formulation achieves new state-of-the-art results for the task (achieving a top-10 accuracy of 73.2% vs. 54.7% by TransE when evaluated on Freebase). Furthermore, we introduce a novel approach that utilizes the learned relation embeddings to mine logical rules from the KB such as "BornInCity(a,b) and CityInCountry(b,c) => Nationality(a,c)". We find that embeddings learned from the bilinear objective are particularly good at capturing relational semantics, and that the composition of relations is characterized by matrix multiplication. More interestingly, we demonstrate that our embedding-based rule extraction approach successfully outperforms a state-of-the-art confidence-based rule mining approach in mining horn rules that involve compositional reasoning."

>	"We examine and compare different types of relation operators and entity vector representations under a general framework for multi-relational learning. Specifically, we derive several recently proposed embedding models, including TransE and NTN, and their variants under the same framework. We empirically evaluate their performance on a knowledge base completion task using various real-world datasets in a controlled experimental setting and present several interesting findings. First, the models with fewer parameters tend to be better than more complex models in terms of both performance and scalability. Second, the bilinear operator plays an important role in capturing entity interactions. Third, with the same model complexity, multiplicative operations are superior to additive operations in modeling relations. Finally, initializing entity vectors with pre-trained phrase vectors can significantly boost performance, whereas representing entity vectors as an average of word vectors that are initialized with pre-trained vectors may hurt performance."

  - http://arxiv.org/pdf/1411.4072.pdf
  - https://github.com/dirkweissenborn/genie-kb/blob/master/model/models.py (DistMult)


#### Nickel, Tresp - ["Tensor Factorization for Multi-Relational Learning"](http://www.ecmlpkdd2013.org/wp-content/uploads/2013/07/673.pdf) (RESCAL model)
>	"Tensor factorization has emerged as a promising approach for solving relational learning tasks. Here we review recent results on a particular tensor factorization approach, i.e. Rescal, which has demonstrated state-of-the-art relational learning results, while scaling to knowledge bases with millions of entities and billions of known facts."

>	"Exploiting the information contained in the relationships between entities has been essential for solving a number of important machine learning tasks. For instance, social network analysis, bioinformatics, and artificial intelligence all make extensive use of relational information, as do large knowledge bases such as Google’s Knowledge Graph or the Semantic Web. It is well-known that, in these and similar domains, statistical relational learning can improve learning results significantly over non-relational methods. However, despite the success of SRL in specific applications, wider adoption has been hindered by multiple factors: without extensive prior knowledge about a domain, existing SRL methods often have to resort to structure learning for their functioning; a process that is both time consuming and error prone. Moreover, inference is often based on methods such as MCMC and variational inference which introduce additional scalability issues. Recently, tensor factorization has been explored as an approach that overcomes some of these problems and that leads to highly scalable solutions. Tensor factorizations realize multi-linear latent factor models and contain commonly used matrix factorizations as the special case of bilinear models. We will discuss tensor factorization for relational learning by the means of Rescal, which is based on the factorization of a third-order tensor. Rescal is highly scalable such that large knowledge bases can be factorized."

>	"RESCAL models each entity with a vector, and each relation with a matrix, and computes the probability of an entity pair belonging to a relation by multiplying the relation matrix on either side with the entity vectors."

>	"RESCAL has cubic computational and quadratic memory complexity with regard to the number of latent components and thus can be applied to problems that require a moderate to large number of latent components."

>	"The rank of an adjacency tensor is lower bounded by the maximum number of strongly connected components of a single relation and upper bounded by the sum of diclique partition numbers of all relations."

  - http://videolectures.net/eswc2014_tresp_machine_learning/ + http://www.dbs.ifi.lmu.de/~tresp/papers/ESWC-Keynote.pdf
  - http://www.cip.ifi.lmu.de/~nickel/iswc2012-slides/#/
  - http://edoc.ub.uni-muenchen.de/16056/1/Nickel_Maximilian.pdf (PhD thesis)
  - http://matt-gardner.github.io/paper-thoughts/2015/01/14/tensor-decomposition.html
  - https://github.com/mnick/scikit-tensor
  - https://github.com/mnick/rescal.py
  - https://github.com/nzhiltsov/Ext-RESCAL + http://nzhiltsov.blogspot.ru/2014/10/ext-rescal-tensor-factorization.html


#### Krompass, Nickel, Tresp - ["Large-Scale Factorization of Type-Constrained Multi-Relational Data"](http://www.dbs.ifi.lmu.de/~tresp/papers/LargeScaleFactorizationOfTypeConstraintMultiRelationalData.pdf)
>	"The statistical modeling of large multi-relational datasets has increasingly gained attention in recent years. Typical applications involve large knowledge bases like DBpedia, Freebase, YAGO and the recently introduced Google Knowledge Graph that contain millions of entities, hundreds and thousands of relations, and billions of relational tuples. Collective factorization methods have been shown to scale up to these large multi-relational datasets, in particular in form of tensor approaches that can exploit the highly scalable alternating least squares algorithms for calculating the factors. In this paper we extend the recently proposed state-of-the-art RESCAL tensor factorization to consider relational type-constraints. Relational type-constraints explicitly define the logic of relations by excluding entities from the subject or object role. In addition we will show that in absence of prior knowledge about type-constraints, local closed-world assumptions can be approximated for each relation by ignoring unobserved subject or object entities in a relation. In our experiments on representative large datasets (Cora, DBpedia), that contain up to millions of entities and hundreds of type-constrained relations, we show that the proposed approach is 
scalable. It further significantly outperforms RESCAL without type-constraints in both, runtime and prediction quality."
>	"We have proposed a general collective factorization approach for large type-constrained multi-relational data that is able to exploit relational type-constraints during factorization. Our experiments showed that in addition to faster convergence we obtained better prediction accuracy and the approach uses less memory, if compared to RESCAL. More precisely, we demonstrated on all datasets that the link prediction quality of the proposed model increased significantly faster with the rank of the factorization than with RESCAL, which generally needed a significantly higher rank to achieve similar AUPRC scores for the link prediction tasks. In case of the very large DBpedia datasets with millions of entities and hundreds of relations, our method was able to make meaningful predictions on a very low-rank of 50, a rank where RESCAL failed. In addition, we showed through our experiments that useful type-constraints can be approximated by defining them based on actual observed subject and object entities in each relation in absence of prior knowledge."

>	"For large multi-relational datasets with a multitude of relations, tensor-based methods have recently been proposed where binary relations are represented as square adjacency matrices that are stacked as frontal slices in a three-way adjacency tensor. Learning is then based on the factorization of this adjacency tensor where highly efficient alternating least squares algorithms can be exploited, which partially utilize closed-form solutions. In most relational learning settings a closed-world assumption is appropriate and missing triples are treated as negative evidence, and here ALS, which is applicable with complete data, is highly efficient. In contrast, when a closed-world assumption is not appropriate, for example when the goal is to predict movie ratings, other approaches such as stochastic gradient descent can be more efficient, where all unobserved ratings are treated as missing. We argue that by exploiting type-constraints, the amount of “trivial” negative evidence (under a closed-world assumption) can be significantly reduced, what makes ALS-based methods very attractive again for large type-constrained data. To the best of our knowledge, there is no ALS algorithm for factorization that exploits closed-form solutions and considers type-constraints during factorization. In addition, in contrast to factorizations that consider every unobserved triple as missing, type-constraints add prior knowledge about relations to the factorization, such that triples that disagree with the type constraints are excluded during factorization. Type-constraints are present in most datasets of interest and imply that for a given relation, only subject entities that belong to a certain domain class and object entities that belong to a certain range class can be related. For instance, the relation marriedTo is restricted to human beings."

>	"By neglecting type-constraints when using ALS under closed-world assumptions, it is very likely that the factorization will need more degrees of freedom (controlled by the rank of the factorization), since the latent vector representations for the entities and their interactions have to account for a huge amount of meaningless unobserved relations between entities. We argue that, especially for larger datasets, the required increase of model complexity will lead to an avoidable high runtime and memory consumption. By focusing only on relevant tuples, high quality latent vector representations can be constructed with a significant reduction in the required degrees of freedom. In this paper we propose a general collective factorization approach for binary relations that exploits relational type-constraints in large multi-relational data by using ALS. In difference to other factorization methods that have also been applied to large scale datasets, it also utilizes closed-form solutions during optimization. The proposed method is capable of factorizing hundreds of adjacency matrices of arbitrary shapes, that represent local closed-world assumptions, into both a shared low-rank latent representation for entities and a representation for the relation-specific interactions of those latent entities."


#### Riedel, Yao, McCallum, Marlin - ["Relation Extraction with Matrix Factorization and Universal Schemas"](http://people.cs.umass.edu/~lmyao/papers/univ-schema-tacl.pdf) (Model E, Model F, Model N)
>	"Traditional relation extraction predicts relations within some fixed and finite target schema. Machine learning approaches to this task require either manual annotation or, in the case of distant supervision, existing structured sources of the same schema. The need for existing datasets can be avoided by using a universal schema: the union of all involved schemas (surface form predicates as in OpenIE, and relations in the schemas of preexisting databases). This schema has an almost unlimited set of relations (due to surface forms), and supports integration with existing structured data (through the relation types of existing databases). To populate a database of such schema we present matrix factorization models that learn latent feature vectors for entity tuples and relations. We show that such latent models achieve substantially higher accuracy than a traditional classification approach. More importantly, by operating simultaneously on relations observed in text and in pre-existing structured DBs such as Freebase, we are able to reason about unstructured and structured data in mutually-supporting ways."

  - http://techtalks.tv/talks/relation-extraction-with-matrix-factorization-and-universal-schemas/58435/ (Riedel)
  - http://youtube.com/watch?v=odI3RznREY4 (Yao)
  - https://github.com/dirkweissenborn/genie-kb/blob/master/model/models.py (Model E, Model F, Model N)


#### Toutanova, Chen, Pantel, Poon, Choudhury, Gamon - ["Representing Text for Joint Embedding of Text and Knowledge Bases"](http://research.microsoft.com/apps/pubs/default.aspx?id=254916)
>	"Models that learn to represent textual and knowledge base relations in the same continuous latent space are able to perform joint inferences among the two kinds of relations and obtain high accuracy on knowledge base completion (Riedel et al., 2013). In this paper we propose a model that captures the compositional structure of textual relations, and jointly optimizes entity, knowledge base, and textual relation representations. The proposed model significantly improves performance over a model that does not share parameters among textual relations with common sub-structure."

>	"Here we explored an alternative representation of textual relations for latent feature models that learn to represent knowledge base and textual relations in the same vector space. We showed that given the large degree of sharing of sub-structure in the textual relations, it was beneficial to compose their continuous representations out of the representations of their component words and dependency arc links. We applied a convolutional neural network model and trained it jointly with a model mapping entities and knowledge base relations to the same vector space, obtaining substantial improvements over an approach that treats the textual relations as atomic units having independent parameterization."

  - http://akbc.ws/2016/slides/toutanova-akbc16.pdf


#### Verga, Belanger, Strubell, Roth, McCallum - ["Multilingual Relation Extraction using Compositional Universal Schema"](http://arxiv.org/abs/1511.06396)
>	"Universal schema builds a knowledge base of entities and relations by jointly embedding all relation types from input KBs as well as textual patterns expressing relations from raw text. In most previous applications of universal schema, each textual pattern is represented as a single embedding, preventing generalization to unseen patterns. Recent work employs a neural network to capture patterns’ compositional semantics, providing generalization to all possible input text. In response, this paper introduces significant further improvements to the coverage and flexibility of universal schema relation extraction: predictions for entities unseen in training and multilingual transfer learning to domains with no annotation. We evaluate our model through extensive experiments on the English and Spanish TAC KBP benchmark, outperforming the top system from TAC 2013 slot-filling using no handwritten patterns or additional annotation. We also consider a multilingual setting in which English training data entities overlap with the seed KB, but Spanish text does not. Despite having no annotation for Spanish data, we train an accurate predictor, with additional improvements obtained by tying word embeddings across languages. Furthermore, we find that multilingual training improves English relation extraction accuracy. Our approach is thus suited to broad-coverage automated knowledge base construction in a variety of languages and domains."

>	"By jointly embedding English and Spanish corpora along with a KB, we can train an accurate Spanish relation extraction model using no direct annotation for relations in the Spanish data. This approach has the added benefit of providing significant accuracy improvements for the English model, outperforming the top system on the 2013 TAC KBC slot filling task, without using the hand-coded rules or additional annotations of alternative systems. By using deep sentence encoders, we can perform prediction for arbitrary input text and for entities unseen in training. Sentence encoders also provides opportunities to improve cross-lingual transfer learning by sharing word embeddings across languages. In future work we will apply this model to many more languages and domains besides newswire text. We would also like to avoid the entity detection problem by using a deep architecture to both identify entity mentions and identify relations between them."


#### Verga, McCallum - ["Row-less Universal Schema"](https://arxiv.org/abs/1604.06361)
>	"Universal schema jointly embeds knowledge bases and textual patterns to reason about entities and relations for automatic knowledge base construction and information extraction. In the past, entity pairs and relations were represented as learned vectors with compatibility determined by a scoring function, limiting generalization to unseen text patterns and entities. Recently, ‘column-less’ versions of Universal Schema have used compositional pattern encoders to generalize to all text patterns. In this work we take the next step and propose a ‘row-less’ model of universal schema, removing explicit entity pair representations. Instead of learning vector representations for each entity pair in our training set, we treat an entity pair as a function of its relation types. In experimental results on the FB15k-237 benchmark we demonstrate that we can match the performance of a comparable model with explicit entity pair representations using a model of attention over relation types. We further demonstrate that the model performs with nearly the same accuracy on entity pairs never seen during training."

>	"In this paper we explore a row-less extension of Universal Schema that forgoes explicit entity pair representations for an aggregation function over relation types. This extension allows prediction between all entity pairs in new textual mentions - whether seen at train time or not - and also provides a natural connection to the provenance supporting the prediction. In this work we show that an aggregation function based on query-specific attention over relation types outperforms query independent aggregations. We show that aggregation models are able to predict on par with entity pair models for seen entity pairs and, in the case of attention, suffer very little loss for unseen entity pairs. We also limited our pattern encoders to lookup-tables. In future work we will combine the column-less and rowless approach to make a fully compositional Universal Schema model. This will allow Universal Schema to generalize to all new textual patterns and entity pairs."

  - http://akbc.ws/2016/slides/verga-akbc16.pdf


#### Verga, Neelakantan, McCallum - ["Generalizing to Unseen Entities and Entity Pairs with Row-less Universal Schema"](https://arxiv.org/abs/1606.05804)
>	"Universal schema predicts the types of entities and relations in a knowledge base by jointly embedding the union of all available schema types---not only types from multiple structured databases (such as Freebase or Wikipedia infoboxes), but also types expressed as textual patterns from raw text. This prediction is typically modeled as a matrix completion problem, with one type per column, and either one or two entities per row (in the case of entity types or binary relation types, respectively). Factorizing this sparsely observed matrix yields a learned vector embedding for each row and each column. In this paper we explore the problem of making predictions for entities or entity-pairs unseen at training time (and hence without a pre-learned row embedding). We propose an approach having no per-row parameters at all; rather we produce a row vector on the fly using a learned aggregation function of the vectors of the observed columns for that row. We experiment with various aggregation functions, including neural network attention models. Our approach can be understood as a natural language database, in that questions about KB entities are answered by attending to textual or database evidence. In experiments predicting both relations and entity types, we demonstrate that despite having an order of magnitude fewer parameters than traditional universal schema, we can match the accuracy of the traditional model, and more importantly, we can now make predictions about unseen rows with nearly the same accuracy as rows available at training time."

>	"In this paper we explore a row-less extension of universal schema that forgoes explicit row representations for an aggregation function over its observed columns. This extension allows prediction between all rows in new textual mentions - whether seen at train time or not - and also provides a natural connection to the provenance supporting the prediction. Our models also have a smaller memory footprint. In this work we show that an aggregation function based on query-specific attention over relation types outperforms query independent aggregations. We show that aggregation models are able to predict on par with models with explicit row representations on seen row entries."

  - http://akbc.ws/2016/slides/verga-akbc16.pdf


#### Singh, Rocktaschel, Riedel - ["Towards Combined Matrix and Tensor Factorization for Universal Schema Relation Extraction"](https://rockt.github.io/pdf/singh2015towards.pdf)
>	"Matrix factorization of knowledge bases in universal schema has facilitated accurate distantly-supervised relation extraction. This factorization encodes dependencies between textual patterns and structured relations using low-dimensional vectors defined for each entity pair; although these factors are effective at combining evidence for an entity pair, they are inaccurate on rare pairs, or for relations that depend crucially on the entity types. On the other hand, tensor factorization is able to overcome these shortcomings when applied to link prediction by maintaining entity-wise factors. However these models have been unsuitable for universal schema. In this paper we first present an illustration on synthetic data that explains the unsuitability of tensor factorization to relation extraction with universal schemas. Since the benefits of tensor and matrix factorization are complementary, we then investigate two hybrid methods that combine the benefits of the two paradigms. We show that the combination can be fruitful: we handle ambiguously phrased relations, achieve gains in accuracy on real-world relations, and demonstrate that entity embeddings encode entity types."

>	"Although tensor factorization has been widely used for knowledge-base completion for structured data, it performs poorly on universal schema for relation extraction. Matrix factorization, on the other hand, is appropriate for the task as it is able to compactly represent the correlations between surface pattern and structured KB relations, however learning pairwise factors is not effective for entity pairs with sparse observations or for identifying latent entity types. We illustrate the differences between these matrix and tensor factorization using simple relations, and further, construct an additional relation that none of these approaches are able to model. Motivated by this need for combining their complementary benefits, we explore two hybrid matrix and tensor factorization approaches. Along with being able to model our constructed relations, these approaches also provided improvements on real-world relation extraction. We further provide qualitative exploration of the entity embedding vectors, showing that the embeddings learn fine-grained entity types from relational data. Our investigations suggest a number of possible avenues for future work. Foremost, we would like to investigate why the hybrid models, which perform significantly better on synthetic data, fail to achieve similar gains on real-world relations. Second, including tensor factorization in the universal schema model enables us to augment the model with external entity information such as observed unary patterns and Freebase types, in order to aid both relation extraction and entity type prediction. Lastly, these hybrid approaches also enable extension of universal schema directly to n-ary relations, allowing a variety of models based on the choice of matrix or tensor representation for each relation."

>	"There are a few shortcomings of models that rely solely on pairwise embeddings. To learn an appropriate representation of an entity-pair, the two entities need to be mentioned together frequently, which is not the case for many entity-pairs of interest. Since predicting relations often relies on the entity types, this lack of ample relational evidence for an entity pair can result in poor estimation of their types, and hence, of their relations. Further, a large number of pairwise relation instances (relative to the number of entities) results in a large number of model parameters, leading to scalability concerns."

>	"Although matrix factorization performs well for universal schema, it is not robust to sparse data and does not capture latent entity types that can be crucial for accurate relation extraction. On the other hand, although tensor factorization models are able to compactly represent entity types using unary embeddings, they are unable to adequately represent the pair-specific information that is necessary for modeling relations."


#### Bouchard, Singh, Trouillon - ["On Approximate Reasoning Capabilities of Low-Rank Vector Spaces"](http://sameersingh.org/files/papers/logicmf-krr15.pdf)
>	"In relational databases, relations between objects, represented by binary matrices or tensors, may be arbitrarily complex. In practice however, there are recurring relational patterns such as transitive, permutation, and sequential relationships, that have a regular structure which is not captured by the classical notion of matrix rank or tensor rank. In this paper, we show that factorizing the relational tensor using a logistic or hinge loss instead of the more standard squared loss is more appropriate because it can accurately model many common relations with a fixed-size embedding (depends sub-linearly on the number of entities in the knowledge base). We illustrate this fact empirically by being able to efficiently predict missing links in several synthetic and real-world experiments. Further, we provide theoretical justification for logistic loss by studying its connection to a complexity measure from the field of information complexity called sign rank. Sign rank is a more appropriate complexity measure as it is low for transitive, permutation, or sequential relationships, while being suitably large, with a high probability, for uniformly sampled binary matrices/tensors."

>	"For a long time, practitioners have been reluctant to use embedding models because many common relationships, including the sameAs relation modeled as an identity matrix, were not trivially seen as low-rank. In this paper we showed that when sign-rank based binary loss is minimized, many common relations such as permutation matrices, sequential relationships, and transitivity can be represented by surprisingly small embeddings."

  - https://youtube.com/watch?v=sKZD8huxjZ0 (Bouchard)
  - https://drive.google.com/file/d/0B_hicYJxvbiObnNYZ0cyMkotUzQ


#### Rocktaschel, Bosnjak, Singh, Riedel - ["Low-Dimensional Embeddings of Logic"](http://www.aclweb.org/anthology/W/W14/W14-2409.pdf)
>	"Many machine reading approaches, from shallow information extraction to deep semantic parsing, map natural language to symbolic representations of meaning. Representations such as first-order logic capture the richness of natural language and support complex reasoning, but often fail in practice due to their reliance on logical background knowledge and the difficulty of scaling up inference. In contrast, low-dimensional embeddings (i.e. distributional representations) are efficient and enable generalization, but it is unclear how reasoning with embeddings could support the full power of symbolic representations such as first-order logic. In this proof-of-concept paper we address this by learning embeddings that simulate the behavior of first-order logic."

  - https://github.com/uclmr/low-rank-logic
  - http://yoavartzi.com/sp14/slides/rockt.sp14.pdf
  - https://b8ca8e88-a-62cb3a1a-s-sites.googlegroups.com/site/learningsemantics2014/SebastianRiedel.pdf
  - http://sameersingh.org/files/papers/lowranklogic-starai14-poster.pdf


#### Rocktaschel, Singh, Riedel - ["Injecting Logical Background Knowledge into Embeddings for Relation Extraction"](http://rockt.github.io/pdf/rocktaschel2015injecting.pdf)
>	"Matrix factorization approaches to relation extraction provide several attractive features: they support distant supervision, handle open schemas, and leverage unlabeled data. Unfortunately, these methods share a shortcoming with all other distantly supervised approaches: they cannot learn to extract target relations without existing data in the knowledge base, and likewise, these models are inaccurate for relations with sparse data. Rule-based extractors, on the other hand, can be easily extended to novel relations and improved for existing but inaccurate relations, through first-order formulae that capture auxiliary domain knowledge. However, usually a large set of such formulae is necessary to achieve generalization. In this paper, we introduce a paradigm for learning low-dimensional embeddings of entity-pairs and relations that combine the advantages of matrix factorization with first-order logic domain knowledge. We introduce simple approaches for estimating such embeddings, as well as a novel training algorithm to jointly optimize over factual and first-order logic information. Our results show that this method is able to learn accurate extractors with little or no distant supervision alignments, while at the same time generalizing to textual patterns that do not appear in the formulae."

>	"Inspired by the benefits of logical background knowledge that can lead to precise extractors, and of distant supervision based matrix factorization that can utilize dependencies between textual patterns to generalize, in this paper we introduced a novel training paradigm for learning embeddings that combine matrix factorization with logic formulae. Along with a deterministic approach to enforce the formulae a priori, we propose a joint objective that rewards predictions that satisfy given logical knowledge, thus learning embeddings that do not require logical inference at test time. Experiments show that the proposed approaches are able to learn extractors for relations with little to no observed textual alignments, while at the same time benefiting more common relations. This research has thrown up many questions in need of further investigation. As opposed to our approach that modifies both relation and entity-pair embeddings, further work needs to explore training methods that only modify relation embeddings in order to encode logical dependencies explicitly, and thus avoid memorization. Although we obtain significant gains by using implications, our approach facilitates the use of arbitrary formulae. Furthermore, we are interested in combining relation extraction with models that learn entity type representations (e.g. tensor factorization or neural models) to allow for expressive logical statements such as ∀x, y: nationality(x, y) ⇒ country(y). Since such common sense formulae are often not directly observed in distant supervision, they can go a long way in fixing common extraction errors. Finally, we will investigate methods to automatically mine commonsense knowledge for injection into embeddings from additional resources such as Probase or directly from text using a semantic parser."

>	"We propose to inject formulae into the embeddings of relations and entity-pairs, i.e., estimate the embeddings such that predictions based on them conform to given logic formulae. We refer to such embeddings as low-rank logic embeddings. Akin to matrix factorization, inference of a fact at test time still amounts to an efficient dot product of the corresponding relation and entity-pair embeddings, and logical inference is not needed. We present two techniques for injecting logical background knowledge, pre-factorization inference and joint optimization, and demonstrate in subsequent sections that they generalize better than direct logical inference, even if such inference is performed on the predictions of the matrix factorization model."

>	"The intuition is that the additional training data generated by the formulae provide evidence of the logical dependencies between relations to the matrix factorization model, while at the same time allowing the factorization to generalize to unobserved facts and to deal with ambiguity and noise in the data. No further logical inference is performed during or after training of the factorization model as we expect that the learned embeddings encode the given formulae. One drawback of pre-factorization inference is that the formulae are enforced only on observed atoms, i.e., first-order dependencies on predicted facts are ignored. Instead we would like to include a loss term for the logical formulae directly in the matrix factorization objective, thus jointly optimizing embeddings to reconstruct factual training data as well as obeying to first-order logical background knowledge."

>	"Even if the embeddings could enable perfect logical reasoning, how do we provide provenance or proofs of answers? Moreover, in practice a machine reader (e.g. a semantic parser) incrementally gathers logical statements from text - how could we incrementally inject this knowledge into embeddings without retraining the whole model? Finally, what are the theoretical limits of embedding logic in vector spaces?"

>	"Matrix factorization for relation extraction generalizes well
>	  - Hard to fix mistakes
>	  - Fails for new or sparse relations
>	Formalize background knowledge as logical formluae
>	  - Easy to modify and improve
>	  - Brittle, no generalization (Markov Logic Networks generalize well but offer possibly intractable inference)
>	Formulae can be injected into embeddings
>	  - Make logical background knowledge differentiable
>	  - Jointly optimize over factual and first-order knowledge
>	  - Learns relations with no or little prior information in databases
>	  - Generalizes beyond textual patterns mentioned in formulae
>	  - Joint optimization >(better) Pre-factorization inference > Post-factorization inference > Logical inference"

  - http://techtalks.tv/talks/injecting-logical-background-knowledge-into-embeddings-for-relation-extraction/61526/ + http://rockt.github.io/slides/2015-naacl.pdf (Rocktaschel)
  - https://github.com/uclmr/low-rank-logic
  - https://b8ca8e88-a-62cb3a1a-s-sites.googlegroups.com/site/learningsemantics2014/SebastianRiedel.pdf
  - http://sameersingh.org/files/papers/lowranklogic-starai14-poster.pdf
  - http://yoavartzi.com/sp14/slides/rockt.sp14.pdf


#### Demeester, Rocktaschel, Riedel - ["Lifted Rule Injection for Relation Embeddings"](https://arxiv.org/abs/1606.08359)
>	"Methods based on representation learning currently hold the state-of-the-art in many natural language processing and knowledge base inference tasks. Yet, a major challenge is how to efficiently incorporate commonsense knowledge into such models. A recent approach regularizes relation and entity representations by propositionalization of first-order logic rules. However, propositionalization does not scale beyond domains with only few entities and rules. In this paper we present a highly efficient method for incorporating implication rules into distributed representations for automated knowledge base construction. We map entity-tuple embeddings into an approximately Boolean space and encourage a partial ordering over relation embeddings based on implication rules mined from WordNet. Surprisingly, we find that the strong restriction of the entity-tuple embedding space does not hurt the expressiveness of the model and even acts as a regularizer that improves generalization. By incorporating few commonsense rules, we achieve an increase of 2 percentage points mean average precision over a matrix factorization baseline, while observing a negligible increase in runtime."

>	"We presented a novel, fast approach for incorporating first-order implication rules into distributed representations of relations. We termed our approach ‘lifted rule injection’, as it avoids the costly grounding of first-order implication rules and is thus independent of the size of the domain of entities. By construction, these rules are satisfied for any observed or unobserved fact. The presented approach requires a restriction on the entity-tuple embedding space. However, experiments on a real-world dataset show that this does not impair the expressiveness of the learned representations. On the contrary, it appears to have a beneficial regularization effect. By incorporating rules generated from WordNet hypernyms, our model improved over a matrix factorization baseline for knowledge base completion. Especially for domains where annotation is costly and only small amounts of training facts are available, our approach provides a way to leverage external knowledge sources for inferring facts. In future work, we want to extend the proposed ideas beyond implications towards general firstorder logic rules. We believe that supporting conjunctions, disjunctions and negations would enable to debug and improve representation learning based knowledge base completion. Furthermore, we want to integrate these ideas into neural methods beyond matrix factorization approaches."


#### Neelakantan, Roth, McCallum - ["Knowledge Base Completion using Compositional Vector Space Models"](http://akbc.ws/2014/submissions/akbc2014_submission_10.pdf) (research for Google Knowledge Vault)
>	"Traditional approaches to knowledge base completion have been based on symbolic representations. Low-dimensional vector embedding models proposed recently for this task are attractive since they generalize to possibly unlimited sets of relations. A significant drawback of previous embedding models for KB completion is that they merely support reasoning on individual relations (e.g., bornIn(X, Y) -> nationality(X, Y)). In this work, we develop models for KB completion that support chains of reasoning on paths of any length using compositional vector space models. We construct compositional vector representations for the paths in the KB graph from the semantic vector representations of the binary relations in that path and perform inference directly in the vector space. Unlike previous methods, our approach can generalize to paths that are unseen in training and, in a zero-shot setting, predict target relations without supervised training data for that relation."

  - http://youtube.com/watch?v=mSrkzc0Nksg (Neelakantan) + https://docs.google.com/file/d/0B_hicYJxvbiOTUxZMWY5T2N2VG8


#### Gardner, Talukdar, Krishnamurthy, Mitchell - ["Incorporating Vector Space Similarity in Random Walk Inference over Knowledge Bases"](http://rtw.ml.cmu.edu/emnlp2014_vector_space_pra/paper.pdf)
>	"Much work in recent years has gone into the construction of large knowledge bases, such as Freebase, DBPedia, NELL, and YAGO. While these KBs are very large, they are still very incomplete, necessitating the use of inference to fill in gaps. Prior work has shown how to make use of a large text corpus to augment random walk inference over KBs. We present two improvements to the use of such large corpora to augment KB inference. First, we present a new technique for combining KB relations and surface text into a single graph representation that is much more compact than graphs used in prior work. Second, we describe how to incorporate vector space similarity into random walk inference over KBs, reducing the feature sparsity inherent in using surface text. This allows us to combine distributional similarity with symbolic logical inference in novel and effective ways. With experiments on many relations from two separate KBs, we show that our methods significantly outperform prior work on KB inference, both in the size of problem our methods can handle and in the quality of predictions made."

  - http://rtw.ml.cmu.edu/emnlp2014_vector_space_pra/ + https://github.com/matt-gardner/pra


#### Guu, Miller, Liang - ["Traversing Knowledge Graphs in Vector Space"](http://arxiv.org/abs/1506.01094)
>	"Path queries on a knowledge graph can be used to answer compositional questions such as “What languages are spoken by people living in Lisbon?”. However, knowledge graphs often have missing facts (edges) which disrupts path queries. Recent models for knowledge base completion impute missing facts by embedding knowledge graphs in vector spaces. We show that these models can be recursively applied to answer path queries, but that they suffer from cascading errors. This motivates a new “compositional” training objective, which dramatically improves all models’ ability to answer path queries, in some cases more than doubling accuracy. On a standard knowledge base completion task, we also demonstrate that compositional training acts as a novel form of structural regularization, reliably improving performance across all base models (reducing errors by up to 43%) and achieving new state-of-the-art results."

>	"We introduced the task of answering path queries on an incomplete knowledge base, and presented a general technique for compositionalizing a broad class of vector space models. Our experiments show that compositional training leads to state-of-the-art performance on both path query answering and knowledge base completion. There are several key ideas from this paper: regularization by augmenting the dataset with paths, representing sets as low-dimensional vectors in a context-sensitive way, and performing function composition using vectors. We believe these three could all have greater applicability in the development of vector space models for knowledge representation and inference."

>	"In this paper, we present a scheme to answer path queries on knowledge bases by “compositionalizing” a broad class of vector space models that have been used for knowledge base completion. At a high level, we interpret the base vector space model as implementing a soft edge traversal operator. This operator can then be recursively applied to predict paths. Our interpretation suggests a new compositional training objective that encourages better modeling of paths. Our technique is applicable to a broad class of composable models that includes the bilinear model (Nickel et al., 2011) and TransE (Bordes et al., 2013)."

>	"We have two key empirical findings: First, we show that compositional training enables us to answer path queries up to at least length 5 by substantially reducing cascading errors present in the base vector space model. Second, we find that somewhat surprisingly, compositional training also improves upon state-of-the-art performance for knowledge base completion, which is a special case of answering unit length path queries. Therefore, compositional training can also be seen as a new form of structural regularization for existing models."

  - https://codalab.org/worksheets/0xfcace41fdeec45f3bc6ddf31107b829f


#### Perozzi, Al-Rfou, Skiena - ["DeepWalk - Online Learning of Social Representations"](http://arxiv.org/abs/1403.6652) (word2vec extension for graph embedding)
>	"We present DeepWalk, a novel approach for learning latent representations of vertices in a network. These latent representations encode social relations in a continuous vector space, which is easily exploited by statistical models. DeepWalk generalizes recent advancements in language modeling and unsupervised feature learning (or deep learning) from sequences of words to graphs. DeepWalk uses local information obtained from truncated random walks to learn latent representations by treating walks as the equivalent of sentences. We demonstrate DeepWalk’s latent representations on several multi-label network classification tasks for social networks such as BlogCatalog, Flickr, and YouTube. Our results show that DeepWalk outperforms challenging baselines which are allowed a global view of the network, especially in the presence of missing information. DeepWalk’s representations can provide F1 scores up to 10% higher than competing methods when labeled data is sparse. In some experiments, DeepWalk’s representations are able to outperform all baseline methods while using 60% less training data. DeepWalk is also scalable. It is an online learning algorithm which builds useful incremental results, and is trivially parallelizable. These qualities make it suitable for a broad class of real world applications such as network classification, and anomaly detection."

  - https://sites.google.com/site/bryanperozzi/projects/deepwalk
  - https://github.com/phanein/deepwalk
  - https://github.com/napsternxg/deepwalk_keras_igraph


#### Atwood, Towsley - ["Search-Convolutional Neural Networks"](http://arxiv.org/abs/1511.02136)
>	"We present a new deterministic relational model derived from convolutional neural networks. Search-Convolutional Neural Networks (SCNNs) extend the notion of convolution to graph search to construct a rich latent representation that extracts local behavior from general graph-structured data. Unlike other neural network models that take graph-structured data as input, SCNNs have a parameterization that is independent of input size, a property that enables transfer learning between datasets. SCNNs can be applied to a wide variety of prediction tasks, including node classification, community detection, and link prediction. Our results indicate that SCNNs can offer considerable lift over off-the-shelf classifiers and simple multilayer perceptrons, and comparable performance to state-of-the-art probabilistic graphical models at considerably lower computational cost."

>	"Structured data present a challenge in machine learning. Models that appropriately represent the underlying structure of an environment often outperform their unstructured counterparts, but finding the right representation and model can be difficult. For instance, convolutional neural networks, which construct features from inputs using the convolution operator, often outperform image classifiers that work directly with the pixels of the input. Generally speaking, CNNs will offer lift when the underlying data are grid-structured and are translationally invariant with respect to the grid. However, it is unclear what researchers should do when the data are not grid-structured."

>	"By defining features via local graph traversals such as breadth-first search and random walks, SCNNs learn latent representations that capture the local behaviors found in graph-structured data."

>	"By constructing a latent representation that encapsulates local behavior in graph-structured data, SCNNs offer comparable performance to state-of-the-art methods for relational classification at considerably lower computational cost. We find that searching the graph via a random walk Laplacian offers more robust performance than either an adjacency matrix or a standard Laplacian, a behavior that we will investigate in future work."

>	"Duvenaud et al. (2015) construct a convolutional model that predicts properties of molecules given their molecular structure. This is a distinct problem domain from the one we consider; rather than classifying based on structure of a graph itself, we make use of local information in a graph of entities to construct a richer representation."

>	"SCNNs also share strong ties to probabilistic relational models (PRMs), a family of graphical models that are capable of representing distributions over complex relational data Koller & Friedman (2009). In contrast with PRMs, SCNNs are deterministic rather than probabilistic, and may represent the first instance of a deterministic relational model. Our results suggest that SCNNs offer comparable performance to partially-observed conditional random fields, the state-of-the-art model for label prediction in relational data."

>	"SCNNs offer comparable empirical performance to partially-observed conditional random fields, the current state-of-the-art method for labeling relational data. SCNNs, however, offer this performance at considerably lower computational cost. Learning the parameters of both SCNNs and partially-observed CRFs involves numerically minimizing a nonconvex objective - the backpropagated error in the case of SCNNs and the negative marginal log-likelihood for CRFs. In practice, the marginal log-likelihood of a partially-observed CRF is usually computed using a contrast-of-partition-functions approach that requires running loopy belief propagation twice; once on the entire graph and once with the observed labels fixed. This algorithm, and thus each step in the numerical optimization, has exponential time complexity O(E*N^C), where E is the number of edges, N is the number of nodes, and C is the size of the maximal clique. In contrast, the learning subroutine for an SCNN requires only a forward and backward pass for each instance in the training data. The complexity is dominated by the matrix multiplication between the graph definition matrix A and the design matrix V, giving an overall polynomial complexity of O(N^2*F). If A is sparse (i.e. node degree is bounded by a constant), then the complexity reduces to O(N*F) and becomes linear with respect to the order of the input graph. This implies that learning an SCNN for a graph containing large cliques will be substantially faster than learning the corresponding CRF."

  - https://github.com/jcatw/scnn



---
### interesting papers - continuous representations of text

#### Neelakantan, Shankar, Passos, McCallum - ["Efficient Non-parametric Estimation of Multiple Embeddings per Word in Vector Space"](https://people.cs.umass.edu/~arvind/emnlp2014.pdf)
>	"There is rising interest in vector-space word embeddings and their use in NLP, especially given recent methods for their fast estimation at very large scale. Nearly all this work, however, assumes a single vector per word type - ignoring polysemy and thus jeopardizing their usefulness for downstream tasks. We present an extension to the Skip-gram model that efficiently learns multiple embeddings per word type. It differs from recent related work by jointly performing word sense discrimination and embedding learning, by non-parametrically estimating the number of senses per word type, and by its efficiency and scalability. We present new state-of-the-art results in the word similarity in context task and demonstrate its scalability by training with one machine on a corpus of nearly 1 billion tokens in less than 6 hours."

  - http://youtube.com/watch?v=EeBj4TyW8B8
  - https://people.cs.umass.edu/~arvind/emnlp2014wordvectors/


#### Tian, Dai, Bian, Gao, Zhang, Chen, Liu - ["A Probabilistic Model for Learning Multi-Prototype Word Embeddings"](http://research.microsoft.com/apps/pubs/default.aspx?id=226629)
>	"Distributed word representations have been widely used and proven to be useful in quite a few natural language processing and text mining tasks. Most of existing word embedding models aim at generating only one embedding vector for each individual word, which, however, limits their effectiveness because huge amounts of words are polysemous (such as bank and star). To address this problem, it is necessary to build multi embedding vectors to represent different meanings of a word respectively. Some recent studies attempted to train multi-prototype word embeddings through clustering context window features of the word. However, due to a large number of parameters to train, these methods yield limited scalability and are inefficient to be trained with big data. In this paper, we introduce a much more efficient method for learning multi embedding vectors for polysemous words. In particular, we first propose to model word polysemy from a probabilistic perspective and integrate it with the highly efficient continuous Skip-Gram model. Under this framework, we design an Expectation-Maximization algorithm to learn the word’s multi embedding vectors. With much less parameters to train, our model can achieve comparable or even better results on word-similarity tasks compared with conventional methods."

>	"In this paper, we introduce a fast and probabilistic method to generate multiple embedding vectors for polysemous words, based on the continuous Skip-Gram model. On one hand, our method addresses the drawbacks of the original Word2Vec model by leveraging multi-prototype word embeddings; on the other hand, our model yields much less complexity without performance loss compared with the former clustering based multi-prototype algorithms. In addition, the probabilistic framework of our method avoids the extra efforts to perform clustering besides training word embeddings."

  - https://github.com/airalcorn2/Deep-Semantic-Similarity-Model


#### Bartunov, Kondrashkin, Osokin, Vetrov - ["Breaking Sticks and Ambiguities with Adaptive Skip-gram"](http://arxiv.org/abs/1502.07257)
>	"Recently proposed Skip-gram model is a powerful method for learning high-dimensional word representations that capture rich semantic relationships between words. However, Skip-gram as well as most prior work on learning word representations does not take into account word ambiguity and maintain only single representation per word. Although a number of Skip-gram modifications were proposed to overcome this limitation and learn multi-prototype word representations, they either require a known number of word meanings or learn them using greedy heuristic approaches. In this paper we propose the Adaptive Skip-gram model which is a nonparametric Bayesian extension of Skip-gram capable to automatically learn the required number of representations for all words at desired semantic resolution. We derive efficient online variational learning algorithm for the model and empirically demonstrate its efficiency on wordsense induction task."

  - http://youtube.com/watch?v=vYbee1InliU (Vetrov)
  - http://postnauka.ru/video/49258 (Vetrov, in russian)
  - http://youtu.be/uoRwjxaDgt0?t=33m58s (Vetrov, in russian)
  - https://github.com/sbos/AdaGram.jl


#### Nalisnick, Ravi - ["Infinite Dimensional Word Embeddings"](http://arxiv.org/abs/1511.05392)
>	"We describe a method for learning word embeddings with stochastic dimensionality. Our Infinite Skip-Gram model specifies an energy-based joint distribution over a word vector, a context vector, and their dimensionality, which can be defined over a countably infinite domain by employing the same techniques used to make the Infinite Restricted Boltzmann Machine tractable. We find that the distribution over embedding dimensionality for a given word is highly interpretable and leads to an elegant probabilistic mechanism for word sense induction. We show qualitatively and quantitatively that the iSG produces parameter-efficient representations that are robust to language’s inherent ambiguity."

>	"We’ve proposed a novel word embedding model called Infinite Skip-Gram that defines vector dimensionality as a random variable with a countably infinite domain. Training via the generalized EM framework allows embeddings to grow as the data requires. This property is especially well suited for learning representations of homographs, which Skip-Gram notably fails at. A unique quality of the iSG is that it is highly interpretable (in comparison to other embedding methods) due to its ability to produce a distribution over the dimensionality of a given word (p(z|w)). Plots of p(z|w) concisely show how specific/vague a word is and its various senses just from the mode landscape."

>	"During training, the iSGM allows word representations to grow naturally based on how well they can predict their context. This behavior enables the vectors of specific words to use few dimensions and the vectors of vague words to elongate as needed. Manual and experimental analysis reveals this dynamic representation elegantly captures specificity, polysemy, and homonymy without explicit definition of such concepts within the model."

  - https://www.evernote.com/shard/s189/sh/2da41f5c-7fc2-4bb1-8c00-dad613404328/e1d1c853162af5fbe537a02796a4ba4e
  - http://dustintran.com/blog/infinite-dimensional-word-embeddings/
  - http://videolectures.net/deeplearning2016_cote_boltzmann_machine/ (Cote)


#### Vilnis, McCallum - ["Word Representations via Gaussian Embedding"](http://arxiv.org/abs/1412.6623)
>	"Current work in lexical distributed representations maps each word to a point vector in low-dimensional space. Mapping instead to a density provides many interesting advantages, including better capturing uncertainty about a representation and its relationships, expressing asymmetries more naturally than dot product or cosine similarity, and enabling more expressive parameterization of decision boundaries. This paper advocates for density-based distributed embeddings and presents a method for learning representations in the space of Gaussian distributions. We compare performance on various word embedding benchmarks, investigate the ability of these embeddings to model entailment and other asymmetric relationships, and explore novel properties of the representation."

>	"In this work we introduced a method to embed word types into the space of Gaussian distributions, and learn the embeddings directly in that space. This allows us to represent words not as low-dimensional vectors, but as densities over a latent space, directly representing notions of uncertainty and enabling a richer geometry in the embedded space. We demonstrated the effectiveness of these embeddings on a linguistic task requiring asymmetric comparisons, as well as standard word similarity benchmarks, learning of synthetic hierarchies, and several qualitative examinations. In future work, we hope to move beyond spherical or diagonal covariances and into combinations of low rank and diagonal matrices. Efficient updates and scalable learning is still possible due to the Sherman-Woodbury-Morrison formula. Additionally, going beyond diagonal covariances will enable us to keep our semantics from being axis-aligned, which will increase model capacity and expressivity. We also hope to move past stochastic gradient descent and warm starting and be able to learn the Gaussian representations robustly in one pass from scratch by using e.g. proximal or block coordinate descent methods. Improved optimization strategies will also be helpful on the highly nonconvex problem of training supervised hierarchies with KL divergence. Representing words and concepts as different types of distributions (including other elliptic distributions such as the Student’s t) is an exciting direction – Gaussians concentrate their density on a thin spherical ellipsoidal shell, which can lead to counterintuitive behavior in high dimensions. Multimodal distributions represent another clear avenue for future work. Combining ideas from kernel methods and manifold learning with deep learning and linguistic representation learning is an exciting frontier. In other domains, we want to extend the use of potential function representations to other tasks requiring embeddings, such as relational learning with the universal schema. We hope to leverage the asymmetric measures, probabilistic interpretation, and flexible training criteria of our model to tackle tasks involving similarity-in-context, comparison of sentences and paragraphs, and more general common sense reasoning."

>	"- represent symbols not as points but as regions in space
>	 - captures uncertainty of representation
>	 - enhances asymmetric reasoning such as entailment/implicature
>	 - more expressive decision boundaries and representational power"

  - http://youtu.be/Xm1XGjc9lDc?t=14m52s (McCallum)
  - http://youtube.com/watch?v=PKTfALFk03M + http://iclr.cc/lib/exe/fetch.php?media=iclr2015:vilnis-iclr2015.pdf (Vilnis)
  - https://github.com/seomoz/word2gauss


#### Trask, Michalak, Liu - ["Sense2Vec - A Fast and Accurate Method for Word Sense Disambiguation in Neural Word Embeddings"](http://arxiv.org/abs/1511.06388)
>	"Neural word representations have proven useful in Natural Language Processing tasks due to their ability to efficiently model complex semantic and syntactic word relationships. However, most techniques model only one representation per word, despite the fact that a single word can have multiple meanings or ”senses”. Some techniques model words by using multiple vectors that are clustered based on context. However, recent neural approaches rarely focus on the application to a consuming NLP algorithm. Furthermore, the training process of recent word-sense models is expensive relative to single-sense embedding processes. This paper presents a novel approach which addresses these concerns by modeling multiple embeddings for each word based on supervised disambiguation, which provides a fast and accurate way for a consuming NLP model to select a sense-disambiguated embedding. We demonstrate that these embeddings can disambiguate both contrastive senses such as nominal and verbal senses as well as nuanced senses such as sarcasm. We further evaluate Part-of-Speech disambiguated embeddings on neural dependency parsing, yielding a greater than 8% average error reduction in unlabeled attachment scores across 6 languages."


#### Huang, He, Gao, Deng, Acero, Heck - ["Learning Deep Structured Semantic Models for Web Search using Clickthrough Data"](http://research.microsoft.com/apps/pubs/default.aspx?id=198202) (DSSM and sent2vec models)
>	"Latent semantic models, such as LSA, intend to map a query to its relevant documents at the semantic level where keyword-based matching often fails. In this study we strive to develop a series of new latent semantic models with a deep structure that project queries and documents into a common low-dimensional space where the relevance of a document given a query is readily computed as the distance between them. The proposed deep structured semantic models are discriminatively trained by maximizing the conditional likelihood of the clicked documents given a query using the clickthrough data. To make our models applicable to large-scale Web search applications, we also use a technique called word hashing, which is shown to effectively scale up our semantic models to handle large vocabularies which are common in such tasks. The new models are evaluated on a Web document ranking task using a real-world data set. Results show that our best model significantly outperforms other latent semantic models, which were considered state-of-the-art in the performance prior to the work presented in this paper."

>	"We present and evaluate a series of new latent semantic models, notably those with deep architectures which we call the DSSM. The main contribution lies in our significant extension of the previous latent semantic models (e.g., LSA) in three key aspects. First, we make use of the clickthrough data to optimize the parameters of all versions of the models by directly targeting the goal of document ranking. Second, inspired by the deep learning framework recently shown to be highly successful in speech recognition, we extend the linear semantic models to their nonlinear counterparts using multiple hidden-representation layers. The deep architectures adopted have further enhanced the modeling capacity so that more sophisticated semantic structures in queries and documents can be captured and represented. Third, we use a letter n-gram based word hashing technique that proves instrumental in scaling up the training of the deep models so that very large vocabularies can be used in realistic web search. In our experiments, we show that the new
techniques pertaining to each of the above three aspects lead to significant performance improvement on the document ranking task. A combination of all three sets of new techniques has led to a new state-of-the-art semantic model that beats all the previously developed competing models with a significant margin."
>	"DSSM stands for Deep Structured Semantic Model, or more general, Deep Semantic Similarity Model. DSSM is a deep neural network modeling technique for representing text strings (sentences, queries, predicates, entity mentions, etc.) in a continuous semantic space and modeling semantic similarity between two text strings (e.g., Sent2Vec). DSSM has wide applications including information retrieval and web search ranking (Huang et al. 2013; Shen et al. 2014a,2014b), ad selection/relevance, contextual entity search and interestingness tasks (Gao et al. 2014a), question answering (Yih et al., 2014), knowledge inference (Yang et al., 2014), image captioning (Fang et al., 2014), and machine translation (Gao et al., 2014b) etc. DSSM can be used to develop latent semantic models that project entities of different types (e.g., queries and documents) into a common low-dimensional semantic space for a variety of machine learning tasks such as ranking and classification. For example, in web search ranking, the relevance of a document given a query can be readily computed as the distance between them in that space. With the latest GPUs from Nvidia, we are able to train our models on billions of words."

>	"Sent2vec maps a pair of short text strings (e.g., sentences or query-answer pairs) to a pair of feature vectors in a continuous, low-dimensional space where the semantic similarity between the text strings is computed as the cosine similarity between their vectors in that space. sent2vec performs the mapping using the Deep Structured Semantic Model (DSSM) or the DSSM with convolutional-pooling structure (CDSSM)."

  - http://research.microsoft.com/en-us/projects/dssm/
  - http://research.microsoft.com/pubs/232372/CIKM14_tutorial_HeGaoDeng.pdf
  - sent2vec: http://research.microsoft.com/en-us/downloads/731572aa-98e4-4c50-b99d-ae3f0c9562b9/default.aspx


#### Heck, Huang - ["Deep Learning of Knowledge Graph Embeddings for Semantic Parsing of Twitter Dialogs"](http://research.microsoft.com/apps/pubs/default.aspx?id=228823)
>	"This paper presents a novel method to learn neural knowledge graph embeddings. The embeddings are used to compute semantic relatedness in a coherence-based semantic parser. The approach learns embeddings directly from structured knowledge representations. A deep neural network approach known as Deep Structured Semantic Modeling is used to scale the approach to learn neural embeddings for all of the concepts (pages) of Wikipedia. Experiments on Twitter dialogs show a 23.6% reduction in semantic parsing errors compared to the state-of-the-art unsupervised approach."

>	"This paper presented a new unsupervised neural knowledge graph embedding model. The new model uses Deep Structured Semantic Modeling to learn the embeddings directly from large-scale knowledge graphs that cover all of Wikipedia. This paper also presented a semantic coherence-based approach for concept disambiguation across multiple dialog turns. When combined with the neural knowledge graph embeddings, the new approach yielded a 23.6% error reduction in the semantic parsing of Twitter dialogs."


#### Hill, Cho, Korhonen, Bengio - ["Learning to Understand Phrases by Embedding the Dictionary"](http://arxiv.org/abs/1504.00548)
>	"Distributional models that learn rich semantic word representations are a success story of recent NLP research. However, developing models that learn useful representations of phrases and sentences has proved far harder. We propose using the definitions found in everyday dictionaries as a means of bridging this gap between lexical and phrasal semantics. We train a recurrent neural network to map dictionary definitions (phrases) to (lexical) representations of the words those definitions define. We present two applications of this architecture: a reverse dictionary, for returning the name of a concept given a definition or description, and a general-knowledge (crossword) question answerer. On both tasks, the RNN trained on definitions from a handful of freely-available lexical resources performs comparably or better than existing commercial systems that rely on major task-specific engineering and far greater memory footprints. This strong performance highlights the general effectiveness of both neural language models and definition-based training for training machines to understand phrases and sentences."

>	"Dictionaries exist in many of the world’s languages. We have shown how these lexical resources can be a valuable resource for training the latest neural language models to interpret and represent the meaning of phrases and sentences. While humans use the phrasal definitions in dictionaries to better understand the meaning of words, machines can use the words to better understand the phrases. We presented an recurrent neural network architecture with a long-short-term memory to explicitly exploit this idea. On the reverse dictionary task that mirrors its training setting, the RNN performs comparably to the best known commercial applications despite having access to many fewer definitions. Moreover, it generates smoother sets of candidates, uses less memory at query time and, perhaps most significantly, requires no linguistic pre-processing or task-specific engineering. We also showed how the description-to-word objective can be used to train models useful for other tasks. The architecture trained additionally on an encyclopedia performs well as a crossword question answerer, outperforming commercial systems on questions containing more than four words. While our QA experiments focused on a particular question type, the results suggest that a similar neural-language-model approach may ultimately lead to improved output from more general QA and dialog systems and information retrieval engines in general. In particular, we propose the reverse dictionary task as a comparatively general-purpose and objective way of evaluating how well models compose lexical meaning into phrase or sentence representations (whether or not they involve training on definitions directly). In the next stage of this research, we will explore ways to enhance the RNN model, especially in the question-answering context. The model is currently not trained on any question-like language, and would conceivably improve on exposure to such linguistic forms. Compared to state-of-the-art word representation learning models, it actually sees very few words during training, and may also benefit from learning from both dictionaries and unstructured text. Finally, we intend to explore ways to endow the model with richer world knowledge. This may require the integration of an external memory module."

  - http://youtube.com/watch?v=H16w6Z2CHkk (Hill)
  - https://github.com/fh295/DefGen2


#### Kiros, Zhu, Salakhutdinov, Zemel, Torralba, Urtasun, Fidler - ["Skip-Thought Vectors"](http://arxiv.org/abs/1506.06726)
>	"We describe an approach for unsupervised learning of a generic, distributed sentence encoder. Using the continuity of text from books, we train an encoder-decoder model that tries to reconstruct the surrounding sentences of an encoded passage. Sentences that share semantic and syntactic properties are thus mapped to similar vector representations. We next introduce a simple vocabulary expansion method to encode words that were not seen as part of training, allowing us to expand our vocabulary to a million words. After training our model, we extract and evaluate our vectors with linear models on 8 tasks: semantic relatedness, paraphrase detection, image-sentence ranking, question-type classification and 4 benchmark sentiment and subjectivity datasets. The end result is an off-the-shelf encoder that can produce highly generic sentence representations that are robust and perform well in practice."

>	"We evaluated the effectiveness of skip-thought vectors as an off-the-shelf sentence representation with linear classifiers across 8 tasks. Many of the methods we compare against were only evaluated on 1 task. The fact that skip-thought vectors perform well on all tasks considered highlight the robustness of our representations. We believe our model for learning skip-thought vectors only scratches the surface of possible objectives. Many variations have yet to be explored, including (a) deep encoders and decoders, (b) larger context windows, (c) encoding and decoding paragraphs, (d) other encoders, such as convnets. It is likely the case that more exploration of this space will result in even higher quality representations."

>	"Developing learning algorithms for distributed compositional semantics of words has been a long-standing open problem at the intersection of language understanding and machine learning. In recent years, several approaches have been developed for learning composition operators that map word vectors to sentence vectors including recursive networks, recurrent networks, convolutional networks and recursive-convolutional methods. All of these methods produce sentence representations that are passed to a supervised task and depend on a class label in order to backpropagate through the composition weights. Consequently, these methods learn high-quality sentence representations but are tuned only for their respective task. The paragraph vector is an alternative to the above models in that it can learn unsupervised sentence representations by introducing a distributed sentence indicator as part of a neural language model. The downside is at test time, inference needs to be performed to compute a new vector. In this paper we abstract away from the composition methods themselves and consider an alternative loss function that can be applied with any composition operator. We consider the following question: is there a task and a corresponding loss that will allow us to learn highly generic sentence representations? We give evidence for this by proposing a model for learning high-quality sentence vectors without a particular supervised task in mind. Using word vector learning as inspiration, we propose an objective function that abstracts the skip-gram model to the sentence level. That is, instead of using a word to predict its surrounding context, we instead encode a sentence to predict the sentences around it. Thus, any composition operator can be substituted as a sentence encoder and only the objective function becomes modified. We call our model skip-thoughts and vectors induced by our model are called skip-thought vectors. Our model depends on having a training corpus of contiguous text."

>	"One difficulty that arises with such an experimental setup is being able to construct a large enough word vocabulary to encode arbitrary sentences. For example, a sentence from a Wikipedia article might contain nouns that are highly unlikely to appear in our book vocabulary. We solve this problem by learning a mapping that transfers word representations from one model to another. Using pretrained word2vec representations learned with a continuous bag-of-words model, we learn a linear mapping from a word in word2vec space to a word in the encoder’s vocabulary space. The mapping is learned using all words that are shared between vocabularies. After training, any word that appears in word2vec can then get a vector in the encoder word embedding space."

##
>	"It turns out that skip-thought vectors have some intriguing properties that allow us to construct F in a really simple way. Suppose we have 3 vectors: an image caption x, a "caption style" vector c and a "book style" vector b. Then we define F as F(x) = x - c + b which intuitively means: keep the "thought" of the caption, but replace the image caption style with that of a story. Then, we simply feed F(x) to the decoder."

  - http://videolectures.net/deeplearning2015_salakhutdinov_deep_learning_2/ (Salakhutdinov, 1:02:56)
  - https://github.com/tensorflow/models/tree/master/skip_thoughts
  - https://github.com/ryankiros/skip-thoughts
  - https://github.com/ryankiros/neural-storyteller + https://medium.com/@samim/generating-stories-about-images-d163ba41e4ed (demo)



---
### interesting papers - question answering over knowledge bases

WebQuestions challenge standings - https://codalab.org/worksheets/0xba659fe363cb46e7a505c5b6a774dc8a/

approaches:
 - entity embedding
 - shallow parsing and retrieval
 - query graph matching
 - query semantic parsing


#### Bordes, Weston, Usunier - ["Open Question Answering with Weakly Supervised Embedding Models"](http://arxiv.org/abs/1404.4326) (entity embedding)
>	"Building computers able to answer questions on any subject is a long standing goal of artificial intelligence. Promising progress has recently been achieved by methods that learn to map questions to logical forms or database queries. Such approaches can be effective but at the cost of either large amounts of human-labeled data or by defining lexicons and grammars tailored by practitioners. In this paper, we instead take the radical approach of learning to map questions to vectorial feature representations. By mapping answers into the same space one can query any knowledge base independent of its schema, without requiring any grammar or lexicon. Our method is trained with a new optimization procedure combining stochastic gradient descent followed by a fine-tuning step using the weak supervision provided by blending automatically and collaboratively generated resources. We empirically demonstrate that our model can capture meaningful signals from its noisy supervision leading to major improvements over Paralex, the only existing method able to be trained on similar weakly labeled data."

  - http://youtu.be/YkVvOBylV5k?t=13m50s + http://akbc.ws/2014/slides/weston-nips-akbc.pdf


#### Bordes, Chopra, Weston - ["Question Answering with Subgraph Embeddings"](http://emnlp2014.org/papers/pdf/EMNLP2014067.pdf) (entity embedding)
>	"This paper presents a system which learns to answer questions on a broad range of topics from a knowledge base using few hand-crafted features. Our model learns low-dimensional embeddings of words and knowledge base constituents; these representations are used to score natural language questions against candidate answers. Training our system using pairs of questions and structured representations of their answers, and pairs of question paraphrases, yields competitive results on a recent benchmark of the literature."

>	"It did as well as the best previous methods on the WebQuestions dataset, yet doesn't use parsers (semantic and/or syntactic) or logic reasoning engines. All it does is some arithmetic over vectors formed from words and relations from both a knowledge base and the question; if finds an optimal "embedding matrix" W, and the it does some matrix multiplication to score question-answer pairs. One limitation is that it doesn't care about word order in the question -- it's basically a "bag of words" setup. Another is that it limits the complexity of the reasoning quite a lot. Another, still, is that it can only spit out entities and paths to get to the answer -- it can't return whole paragraphs, for instance."

  - http://youtu.be/YkVvOBylV5k?t=16m17s (Weston)
  - http://www.shortscience.org/paper?bibtexKey=journals%2Fcorr%2F1406.3676


#### Yih, He, Meek - ["Semantic Parsing for Single-Relation Question Answering"](http://research.microsoft.com/pubs/214353/SingleRelationQA-YihHeMeek-ACL14.pdf) (entity embedding)
>	"We develop a semantic parsing framework based on semantic similarity for open domain question answering. We focus on single-relation questions and decompose each question into an entity mention and a relation pattern. Using convolutional neural network models, we measure the similarity of entity mentions with entities in the knowledge base and the similarity of relation patterns and relations in the KB. We score relational triples in the KB using these measures and select the top scoring relational triple to answer the question. When evaluated on an open-domain QA task, our method achieves higher precision across different recall points compared to the previous approach, and can improve F1 by 7 points."

>	"In this work, we propose a semantic parsing framework for single-relation questions. Compared to the existing work, our key insight is to match relation patterns and entity mentions using a semantic similarity function rather than lexical rules. Our similarity model is trained using convolutional neural networks with letter-trigrams vectors. This design helps the model go beyond bag-of-words representations and handles the OOV issue. Our method achieves higher precision on the QA task than the previous work, Paralex, consistently at different recall points.
>	Despite the strong empirical performance, our system has room for improvement. For instance, due to the variety of entity mentions in the real world, the parallel corpus derived from the WikiAnswers data and ReVerb KB may not contain enough data to train a robust entity linking model. Replacing this component with a dedicated entity linking system could improve the performance and also reduce the number of pattern/mention candidates when processing each question."


#### Yao, van Durme - ["Information Extraction over Structured Data: Question Answering with Freebase"](https://www.cs.jhu.edu/~xuchen/paper/yao-jacana-freebase-acl2014.pdf) (shallow parsing and retrieval)
>	"Answering natural language questions using the Freebase knowledge base has recently been explored as a platform for advancing the state of the art in open domain semantic parsing. Those efforts map questions to sophisticated meaning representations that are then attempted to be matched against viable answer candidates in the knowledge base. Here we show that relatively modest information extraction techniques, when paired with a web-scale corpus, can outperform these sophisticated approaches by roughly 34% relative gain."

>	"We proposed an automatic method for Question Answering from structured data source. Our approach associates question features with answer patterns described by Freebase and has achieved state-of-the-art results on a balanced and realistic QA corpus. To compensate for the problem of domain mismatch or overfitting, we exploited ClueWeb, mined mappings between KB relations and natural language text, and showed that it helped both relation prediction and answer extraction. Our method employs relatively lightweight machinery but has good performance. We hope that this result establishes a new baseline against which semantic parsing researchers can measure their progress towards deeper language understanding and answering of human questions."


#### Fader, Zettlemoyer, Etzioni - ["Open Question Answering Over Curated and Extracted Knowledge Bases"](http://homes.cs.washington.edu/~lsz/papers/fze-kdd14.pdf) (shallow parsing and retrieval)
>	"We consider the problem of open-domain question answering over massive knowledge bases. Existing approaches use either manually curated KBs like Freebase or KBs automatically extracted from unstructured text. In this paper, we present OQA, the first approach to leverage both curated and extracted KBs. A key technical challenge is designing systems that are robust to the high variability in both natural language questions and massive KBs. OQA achieves robustness by decomposing the full Open QA problem into smaller sub-problems including question paraphrasing and query reformulation. OQA solves these sub-problems by mining millions of rules from an unlabeled question corpus and across multiple KBs. OQA then learns to integrate these rules by performing discriminative training on question-answer pairs using a latent-variable structured perceptron algorithm. We evaluate OQA on three benchmark question sets and demonstrate that it achieves up to twice the precision and recall of a state-of-the-art Open QA system."

  - http://videolectures.net/kdd2014_fader_knowledge_bases/
  - https://github.com/afader/oqa/


#### Reddy, Lapata, Steedman - ["Large-scale Semantic Parsing without Question-Answer Pairs"](http://sivareddy.in/papers/reddy2014semanticparsing.pdf) (query graph matching)
>	"In this paper we introduce a novel semantic parsing approach to query Freebase in natural language without requiring manual annotations or question-answer pairs. Our key insight is to represent natural language via semantic graphs whose topology shares many commonalities with Freebase. Given this representation, we conceptualize semantic parsing as a graph matching problem. Our model converts sentences to semantic graphs using CCG and subsequently grounds them to Freebase guided by denotations as a form of weak supervision. Evaluation experiments on a subset of the FREE917 and WebQuestions benchmark datasets show our semantic parser improves over the state of the art."

>	"In this paper, we introduce a new semantic parsing approach for Freebase. A key idea in our work is to exploit the structural and conceptual similarities between natural language and Freebase through a common graph-based representation. We formalize semantic parsing as a graph matching problem and learn a semantic parser without using annotated question-answer pairs. We have shown how to obtain graph representations from the output of a CCG parser and subsequently learn their correspondence to Freebase using a rich feature set and their denotations as a form of weak supervision. Our parser yields state-of-the art performance on three large Freebase domains and is not limited to question answering. We can create semantic parses for any type of NL sentences. Our work brings together several strands of research. Graph-based representations of sentential meaning have recently gained some attention in the literature (Banarescu'2013), and attempts to map sentences to semantic graphs have met with good inter-annotator agreement. Our work is also closely related to Kwiatkowski'2013, Berant and Liang'2014 who present open-domain semantic parsers based on Freebase and trained on QA pairs. Despite differences in formulation and model structure, both approaches have explicit mechanisms for handling the mismatch between natural language and the KB (e.g., using logical-type equivalent operators or paraphrases). The mismatch is handled implicitly in our case via our graphical representation which allows for the incorporation of all manner of powerful features. More generally, our method is based on the assumption that linguistic structure has a correspondence to Freebase structure which does not always hold (e.g., in Who is the grandmother of Prince William?, grandmother is not directly expressed as a relation in Freebase). Additionally, our model fails when questions are too short without any lexical clues (e.g., What did Charles Darwin do?). Supervision from annotated data or paraphrasing could improve performance in such cases. In the future, we plan to explore cluster-based semantics (Lewis and Steedman'2013) to increase the robustness on unseen NL predicates. Our work joins others in exploiting the connections between natural language and open-domain knowledge bases. Recent approaches in relation extraction use distant supervision from a knowledge base to predict grounded relations between two target entities. During learning, they aggregate sentences containing the target entities, ignoring richer contextual information. In contrast, we learn from each individual sentence taking into account all entities present, their relations, and how they interact. Krishnamurthy and Mitchell'2012 formalize semantic parsing as a distantly supervised relation extraction problem combined with a manually specified grammar to guide semantic parse composition. Finally, our approach learns a model of semantics guided by denotations as a form of weak supervision."

  - https://youtube.com/watch?v=hS6oq-nupFw (Reddy)
  - http://techtalks.tv/talks/large-scale-semantic-parsing-without-question-answer-pairs/61530/ (Reddy)


#### Yih, Chang, He, Gao - ["Semantic Parsing via Staged Query Graph Generation: Question Answering with Knowledge Base"](http://research.microsoft.com/apps/pubs/default.aspx?id=244749) (query graph matching)
>	"We propose a novel semantic parsing framework for question answering using a knowledge base. We define a query graph that resembles subgraphs of the knowledge base and can be directly mapped to a logical form. Semantic parsing is reduced to query graph generation, formulated as a staged search problem. Unlike traditional approaches, our method leverages the knowledge base in an early stage to prune the search space and thus simplifies the semantic matching problem. By applying an advanced entity linking system and a deep convolutional neural network model that matches questions and predicate sequences, our system outperforms previous methods substantially, and achieves an F1 measure of 52.5% on the WebQuestions dataset."

>	"In the future, we would like to extend our query graph to represent more complicated questions, and explore more features and models for matching constraints and aggregation functions. Applying other structured-output prediction methods to graph generation will also be investigated."

>	"Query graph that represents the question:
>	- Identify possible entities in the question (e.g., Meg, Family Guy)
>	- Only search relations around these entities in the KB
>	- Narrow down the search space significantly
>	Matching (multi-hop) relations: concatenate multiple relations to a long relation on-the-fly, the DSSM takes care the issues of aggregating semantics from individual relations.
>	DSSM measures the semantic matching between Pattern and Relation."

  - http://research.microsoft.com/pubs/244749/ACL-15-STAGG_deck.pptx


#### Li, Clark - ["Answering Elementary Science Questions by Constructing Coherent Scenes using Background Knowledge"](http://allenai.org/content/publications/EMNLP2015_SceneQA_CameraReady.pdf) (query graph matching)
>	"Much of what we understand from text is not explicitly stated. Rather, the reader uses his/her knowledge to fill in gaps and create a coherent, mental picture or “scene” depicting what text appears to convey. The scene constitutes an understanding of the text, and can be used to answer questions that go beyond the text. Our goal is to answer elementary science questions, where this requirement is pervasive; A question will often give a partial description of a scene and ask the student about implicit information. We show that by using a simple “knowledge graph” representation of the question, we can leverage several large-scale linguistic resources to provide missing background knowledge, somewhat alleviating the knowledge bottleneck in previous approaches. The coherence of the best resulting scene, built from a question/answer-candidate pair, reflects the confidence that the answer candidate is correct, and thus can be used to answer multiple choice questions. Our experiments show that this approach outperforms competitive algorithms on several datasets tested. The significance of this work is thus to show that a simple “knowledge graph” representation allows a version of “interpretation as scene construction” to be made viable."

>	"Elementary grade science tests are challenging as they test a wide variety of commonsense knowledge that human beings largely take for granted, yet are very difficult for machines. For example, consider a question from a NY Regents 4th Grade science test. Question 1: “When a baby shakes a rattle, it makes a noise. Which form of energy was changed to sound energy?” [Answer: mechanical energy] Science questions are typically quite different from the entity-centric factoid questions extensively studied in the question answering community, e.g., “In which year was Bill Clinton born?” While factoid questions are usually answerable from text search or fact databases, science questions typically require deeper analysis. A full understanding of the above question involves not just parsing and semantic interpretation; it involves adding implicit information to create an overall picture of the “scene” that the text is intended to convey, including facts such as: noise is a kind of sound, the baby is holding the rattle, shaking involves movement, the rattle is making the noise, movement involves mechanical energy, etc. This mental ability to create a scene from partial information is at the heart of natural language understanding, which is essential for answering these kinds of question. It is also very difficult for a machine because it requires substantial world knowledge, and there are often many ways a scene can be elaborated."

>	"We present a method for answering multiplechoice questions that implements a simple version of this. A scene is represented as a “knowledge graph” of nodes (words) and relations, and the scene is elaborated with (node, relation, node) tuples drawn from three large-scale linguistic knowledge resources: WordNet, DART, and the FreeAssociation database. These elaborations reflect the mental process of “filling in the gaps”, and multiple choice questions can then be answered by finding which answer option creates the most coherent scene. The notion of NLU as constructing a most coherent scene is not new, and has has been studied in several contexts including work on scripts, interpretation as abduction, bridging anaphora, and paragraph understanding. These methods are inspiring, but have previously been limited by the lack of background knowledge to supply implicit information, and with the complexity of their representations. To make progress, we have chosen to work with a simple “knowledge graph” representation of nodes (words) and edges (relations). Although we lose some subtlety of expression, we gain the ability to leverage several vast resources of world knowledge to supply implicit information. The significance of this work is thus to show that, by working with a simple “knowledge graph” representation, we can make a viable version of “interpretation as scene construction”. Although the approach makes several simplifying assumptions, our experiments show that it outperforms competitive algorithms on several datasets of (real) elementary science questions."

>	"There are clearly many limitations with our approach: we are largely ignoring syntactic structure in the questions; the KBs are noisy, contributing errors to the scenes; the graph representation has limited expressivity (e.g., no quantification or negation); the word2vec measure of relationship strength does not account for the question context; and contradictions are not detected within the scene. These all contributed to QA failures in the tests."


#### Liang, Jordan, Klein - ["Learning Dependency-Based Compositional Semantics"](http://arxiv.org/abs/1109.6841) (query semantic parsing)
>	"Suppose we want to build a system that answers a natural language question by representing its semantics as a logical form and computing the answer given a structured database of facts. The core part of such a system is the semantic parser that maps questions to logical forms. Semantic parsers are typically trained from examples of questions annotated with their target logical forms, but this type of annotation is expensive. Our goal is to learn a semantic parser from question-answer pairs instead, where the logical form is modeled as a latent variable. Motivated by this challenging learning problem, we develop a new semantic formalism, dependency-based compositional semantics, which has favorable linguistic, statistical, and computational properties. We define a log-linear distribution over DCS logical forms and estimate the parameters using a simple procedure that alternates between beam search and numerical optimization. On two standard semantic parsing benchmarks, our system outperforms all existing state-of-the-art systems, despite using no annotated logical forms."

  - http://youtube.com/watch?v=z4XCjlCeGkQ


#### Kwiatkowski, Choi, Artzi, Zettlemoyer - ["Scaling Semantic Parsers with On-the-fly Ontology Matching"](http://yoavartzi.com/pub/kcaz-emnlp.2013.pdf) (query semantic parsing)
>	"We consider the challenge of learning semantic parsers that scale to large, open-domain problems, such as question answering with Freebase. In such settings, the sentences cover a wide variety of topics and include many phrases whose meaning is difficult to represent in a fixed target ontology. For example, even simple phrases such as ‘daughter’ and ‘number of people living in’ cannot be directly represented in Freebase, whose ontology instead encodes facts about gender, parenthood, and population. In this paper, we introduce a new semantic parsing approach that learns to resolve such ontological mismatches. The parser is learned from question-answer pairs, uses a probabilistic CCG to build linguistically motivated logical form meaning representations, and includes an ontology matching model that adapts the output logical forms for each target ontology. Experiments demonstrate state-of-the-art performance on two benchmark semantic parsing datasets, including a nine point accuracy improvement on a recent Freebase QA corpus."

  - https://youtube.com/watch?v=-J1P6MpZEoQ (Choi)


#### Berant, Liang - ["Semantic Parsing via Paraphrasing"](http://cs.stanford.edu/~pliang/papers/paraphrasing-acl2014.pdf) (query semantic parsing)
>	"A central challenge in semantic parsing is handling the myriad ways in which knowledge base predicates can be expressed. Traditionally, semantic parsers are trained primarily from text paired with knowledge base information. Our goal is to exploit the much larger amounts of raw text not tied to any knowledge base. In this paper, we turn semantic parsing on its head. Given an input utterance, we first use a simple method to deterministically generate a set of candidate logical forms with a canonical realization in natural language for each. Then, we use a paraphrase model to choose the realization that best paraphrases the input, and output the corresponding logical form. We present two simple paraphrase models, an association model and a vector space model, and train them jointly from question-answer pairs. Our system PARASEMPRE improves state-of-the-art accuracies on two recently released question-answering datasets."

>	"In this work, we approach the problem of semantic parsing from a paraphrasing viewpoint. A fundamental motivation and long standing goal of the paraphrasing and RTE communities has been to cast various semantic applications as paraphrasing/textual entailment."

>	"In this work, an intermediate representation is employed to handle the mismatch, but instead of logical representation, we opt for a text-based one. Our choice allows us to benefit from the parallel monolingual corpus PARALEX and from word vectors trained on Wikipedia. We believe that our approach is particularly suitable for scenarios such as factoid question answering, where the space of logical forms is somewhat constrained and a few generation rules suffice to reduce the problem to paraphrasing."

>	"Since we train from question-answer pairs, we collect answers by executing the gold logical forms against Freebase. We execute λ-DCS queries by converting them into SPARQL and executing them against a copy of Freebase using the Virtuoso database engine."

  - http://youtube.com/watch?v=JANpOGFOR_E (Berant)
  - http://nlp.stanford.edu/joberant/homepage_files/talks/facebook_jun14.pdf
  - http://www-nlp.stanford.edu/software/sempre/


#### Yang, Duan, Zhou, Rim - ["Joint Relational Embeddings for Knowledge-based Question Answering"](http://emnlp2014.org/papers/pdf/EMNLP2014071.pdf) (query semantic parsing)
>	"Transforming a natural language question into a corresponding logical form is central to the knowledge-based question answering task. Unlike most previous methods that achieve this goal based on mappings between lexicalized phrases and logical predicates, this paper goes one step further and proposes a novel embedding-based approach that maps NL-questions into LFs for KB-QA by leveraging semantic associations between lexical representations and KB properties in the latent space. Experimental results demonstrate that our proposed method outperforms three KB-QA baseline methods on two publicly released QA data sets."

>	"In this paper, we propose a novel method that transforms NL-questions into their corresponding logical forms using joint relational embeddings. We also built a simple and robust KB-QA system based on only the learned embeddings. Such embeddings learn the semantic associations between natural language statements and KB-properties from NLE-KB pairs that are automatically extracted from English WIKIPEDIA using KB-triples with weak supervision. Then, we generate all possible structured queries derived from latent logical features of the given NL-question, and rank them based on the similarity scores between those relational attributes. The experimental results show that our method outperforms the latest three KB-QA baseline systems. For our future work, we will build concept-level context embeddings by leveraging latent meanings of NLEs rather than their surface n-grams with the aligned logical features on KB."


#### Liang - ["Learning to Execute Natural Language"](http://www.iclr.cc/lib/exe/fetch.php?media=iclr2015:percy-liang-iclr2015.pdf) (query semantic parsing)
>	"A natural language utterance can be thought of as encoding a program, whose execution yields its meaning. For example, "the tallest mountain" denotes a database query whose execution on a database produces "Mt. Everest." We present a framework for learning semantic parsers that maps utterances to programs, but without requiring any annotated programs. We first demonstrate this paradigm on a question answering task on Freebase. We then show how that the same framework can be extended to the more ambitious problem of querying semi-structured Wikipedia tables. We believe that our work provides a both a practical way to build natural language interfaces and an interesting perspective on language learning that links language with desired behavior."

  - http://youtu.be/-dj4ctqofIc + http://youtu.be/xKCxF97yvPc
  - http://youtube.com/watch?v=seA3RT98beo


#### Wang, Yan, Wang, Huang - ["An Overview of Microsoft Deep QA System on Stanford WebQuestions Benchmark"](http://research.microsoft.com/pubs/228312/Microsoft%20Deep%20QA.pdf) (query semantic parsing + entity embedding)
>	"Question answering over an existing knowledge base such as Microsoft Satori or open Freebase is one of the most important natural language processing applications. There are approaches based on web-search motivated statistic techniques as well as linguistically oriented knowledge engineering. Both methods face the key challenge on how to handle diverse ways of naturally expressing predicates and entities existing in the KB. The domain independent web information extracted from the massive amount of web usage data can be used with traditional semantic parsing through a unified framework. We provide such a unified framework utilizing both statistically motivated information-theoretic embeddings and logically driven proof-theoretic decoding to significantly improve Stanford’s WebQuestions QA benchmark. In comparison to Stanford’s state of the art ParaSempre 39.9 (F1-score), our Deep QA system achieves 45.3 on the same test data and protocol."



---
### interesting papers - question answering over texts

[machine reading methods and datasets](http://matt-gardner.github.io/paper-thoughts/2016/12/08/reading-comprehension-survey.html)  


#### Gauthier, Mordatch - ["A Paradigm for Situated and Goal-Driven Language Learning"](https://arxiv.org/abs/1610.03585)
>	"A distinguishing property of human intelligence is the ability to flexibly use language in order to communicate complex ideas with other humans in a variety of contexts. Research in natural language dialogue should focus on designing communicative agents which can integrate themselves into these contexts and productively collaborate with humans. In this abstract, we propose a general situated language learning paradigm which is designed to bring about robust language agents able to cooperate productively with humans. This dialogue paradigm is built on a utilitarian definition of language understanding. Language is one of multiple tools which an agent may use to accomplish goals in its environment. We say an agent “understands” language only when it is able to use language productively to accomplish these goals. Under this definition, an agent’s communication success reduces to its success on tasks within its environment. This setup contrasts with many conventional natural language tasks, which maximize linguistic objectives derived from static datasets. Such applications often make the mistake of reifying language as an end in itself. The tasks prioritize an isolated measure of linguistic intelligence (often one of linguistic competence, in the sense of Chomsky), rather than measuring a model’s effectiveness in real-world scenarios. Our utilitarian definition is motivated by recent successes in reinforcement learning methods. In a reinforcement learning setting, agents maximize success metrics on real-world tasks, without requiring direct supervision of linguistic behavior."

>	"We outlined a paradigm for grounded and goal-driven language learning in artificial agents. The paradigm is centered around a utilitarian definition of language understanding, which equates language understanding with the ability to cooperate with other language users in real-world environments. This position demotes language from its position as a separate task to be solved to one of several communicative tools agents might use to accomplish their real-world goals. While this paradigm does already capture a small amount of recent work in dialogue, on the whole it has not received the focus it deserves in the research communities of natural language processing and machine learning. We hope this paper brings focus to the task of situated language learning as a way forward for research in natural language dialogue."


#### Weston, Bordes, Chopra, Mikolov - ["Towards AI-Complete Question Answering: A Set of Prerequisite Toy Tasks"](http://arxiv.org/abs/1502.05698)
>	"One long-term goal of machine learning research is to produce methods that are applicable to reasoning and natural language, in particular building an intelligent dialogue agent. To measure progress towards that goal, we argue for the usefulness of a set of proxy tasks that evaluate reading comprehension via question answering. Our tasks measure understanding in several ways: whether a system is able to answer questions via chaining facts, simple induction, deduction and many more. The tasks are designed to be prerequisites for any system that aims to be capable of conversing with a human. We believe many existing learning systems can currently not solve them, and hence our aim is to classify these tasks into skill sets, so that researchers can identify (and then rectify) the failings of their systems. We also extend and improve the recently introduced Memory Networks model, and show it is able to solve some, but not all, of the tasks."

>	"Despite great recent advances, the road towards intelligent machines able to reason and adapt in real-time in multimodal environments remains long and uncertain. This final goal is so complex and further away that it is impossible to perform experiments and research directly in the desired final conditions, so one has to use intermediate and/or proxy tasks as midway goals. Some of those tasks like object detection in computer vision, or machine translation in natural language processing are very useful on their own and fuel many applications. However, such intermediate tasks are already very difficult and it is not obvious that they are suited testbeds for designing intelligent systems: their inherent complexity makes it hard to precisely interpret the behavior and true capabilities of algorithms, in particular regarding key sophisticated capabilities like reasoning and planning. We advocate the use of controlled artificial environments for developing research in AI, environments in which one can precisely study the behavior of algorithms and unambiguously assess their abilities."

  - http://fb.ai/babi
  - http://youtube.com/watch?v=d-Ma5PkDKG4 + http://youtube.com/watch?v=0RGqJIhdva4 (Bordes) + http://iclr.cc/lib/exe/fetch.php?media=iclr2015:abordes-iclr2015.pdf
  - https://github.com/fchollet/keras/blob/master/examples/babi_memnn.py
  - http://smerity.com/articles/2015/keras_qa.html + https://github.com/fchollet/keras/blob/master/examples/babi_rnn.py


#### Grefenstette, Blunsom, Freitas, Hermann - ["A Deep Architecture for Semantic Parsing"](http://arxiv.org/abs/1404.7296)
>	"Many successful approaches to semantic parsing build on top of the syntactic analysis of text, and make use of distributional representations or statistical models to match parses to ontology-specific queries. This paper presents a novel deep learning architecture which provides a semantic parsing system through the union of two neural models of language semantics. It allows for the generation of ontology-specific queries from natural language statements and questions without the need for parsing, which makes it especially suitable to grammatically malformed or syntactically atypical text, such as tweets, as well as permitting the development of semantic parsers for resource-poor languages."

>	"The ubiquity of always-online computers in the form of smartphones, tablets, and notebooks has boosted the demand for effective question answering systems. This is exemplified by the growing popularity of products like Apple’s Siri or Google’s Google Now services. In turn, this creates the need for increasingly sophisticated methods for semantic parsing. Recent work has answered this call by progressively moving away from strictly rule-based semantic parsing, towards the use of distributed representations in conjunction with traditional grammatically-motivated re-write rules. This paper seeks to extend this line of thinking to its logical conclusion, by providing the first (to our knowledge) entirely distributed neural semantic generative parsing model. It does so by adapting deep learning methods from related work in sentiment analysis, document classification, frame-semantic parsing, and machine translation, combining two empirically successful deep learning models to form a new architecture for semantic parsing."

>	"We begin by introducing two deep learning models with different aims, namely the joint learning of embeddings in parallel corpora, and the generation of strings of a language conditioned on a latent variable, respectively. We then discuss how both models can be combined and jointly trained to form a deep learning model supporting the generation of knowledgebase queries from natural language questions."


#### Yu, Hermann, Blunsom, Pulman - ["Deep Learning for Answer Sentence Selection"](http://arxiv.org/abs/1412.1632)
>	"Answer sentence selection is the task of identifying sentences that contain the answer to a given question. This is an important problem in its own right as well as in the larger context of open domain question answering. We propose a novel approach to solving this task via means of distributed representations, and learn to match questions with answers by considering their semantic encoding. This contrasts prior work on this task, which typically relies on classifiers with large numbers of hand-crafted syntactic and semantic features and various external resources. Our approach does not require any feature engineering nor does it involve specialist linguistic data, making this model easily applicable to a wide range of domains and languages. Experimental results on a standard benchmark dataset from TREC demonstrate that despite its simplicity our model matches state of the art performance on the answer sentence selection task."


#### Feng, Xiang, Glass, Wang, Zhou - ["Applying Deep Learning to Answer Selection: A Study and an Open Task"](http://arxiv.org/abs/1508.01585) (IBM Watson)
>	"We apply a general deep learning framework to address the non-factoid question answering task. Our approach does not rely on any linguistic tools and can be applied to different languages or domains. Various architectures are presented and compared. We create and release a QA corpus and setup a new QA task in the insurance domain. Experimental results demonstrate superior performance compared to the baseline methods and various technologies give further improvements. For this highly challenging task, the top-1 accuracy can reach up to 65.3% on a test set, which indicates a great potential for practical use."

>	"In this paper, the spoken question answering system is studied from an answer selection perspective by employing a deep learning framework. The proposed framework does not rely on any linguistic tool and can be easily adapted to different languages or domains. Our work serves as solid evidence that deep learning based QA is an encouraging research direction. The scientific contributions can be summarized as follows: (1) creating a new QA task in the insurance domain and releasing a new corpus so that different methods can be fairly compared; (2) proposing a general deep learning framework with several variants for the QA task and comparison experiments have been conducted; (3) utilizing novel techniques that bring improvements: multi-layer CNN with layer-wise supervision, augmented CNN with discontinuous convolution and novel similarity metric that combine both L2-norm and inner product information; (4) the best scores in this paper are very promising: for this challenging task (select one answer from a pool with size 500), the top one accuracy of test corpus can reach up to 65.3%; (5) for researchers who want to proceed with this task, this paper provides valuable guidance: a shared layer structure should be adopted; no need to append a hidden layer after the CNN; two levels of CNN with layerwise training improves accuracy; discontinuous convolution sometimes can help; the similarity metric plays a crucial role and the proposed metric is preferred and finally increasing the filter quantity brings improvement."


#### Tan, Santos, Xiang, Zhou - ["LSTM-based Deep Learning Models for Non-Factoid Answer Selection"](http://arxiv.org/abs/1511.04108) (RNN-CNN model, IBM Watson)
>	"In this paper, we apply a general deep learning framework for the answer selection task, which does not depend on manually defined features or linguistic tools. The basic framework is to build the embeddings of questions and answers based on bidirectional long short-term memory (biLSTM) models, and measure their closeness by cosine similarity. We further extend this basic model in two directions. One direction is to define a more composite representation for questions and answers by combining convolutional neural network with the basic framework. The other direction is to utilize a simple but efficient attention mechanism in order to generate the answer representation according to the question context. Several variations of models are provided. The models are examined by two datasets, including TREC-QA and InsuranceQA. Experimental results demonstrate that the proposed models substantially outperform several strong baselines."

>	"This framework is based on building bidirectional long short term memory (biLSTM) models on both questions and answers respectively, connecting with a pooling layer and utilizing a similarity metric to measure the matching degree. We improve this basic model from two perspectives. Firstly, a simple pooling layer may suffer from the incapability of keeping the local linguistic information. In order to give more composite embeddings for questions and answers, we build a convolutional neural network structure on top of biLSTM. Secondly, in order to better distinguish candidate answers according to the question, we introduce a simple but efficient attention model to this framework for the answer embedding generation according to the question context."

>	"There were prior methods using deep learning technologies for the answer selection task. The approaches for non-factoid question answering generally pursue the solution on the following directions: Firstly, the question and answer representations are learned and matched by certain similarity metrics (Feng et al., 2015; Yu et al., 2014; dos Santos et al., 2015). Secondly, a joint feature vector is constructed based on both the question and the answer, and then the task can be converted into a classification or learning-to-rank problem (Wang & Nyberg, 2015). Finally, recently proposed models for textual generation can intrinsically be used for answer selection and generation (Bahdanau et al., 2015; Vinyals & Le, 2015). The framework proposed in this work belongs to the first category. There are two major differences between our approaches and the work in (Feng et al., 2015): (1) The architectures developed in (Feng et al., 2015) are only based on CNN, whereas our models are based on bidirectional LSTMs, which are more capable of exploiting long-range sequential context information. Moreover, we also integrate the CNN structures on the top of biLSTM for better performance. (2) Feng et al. (2015) tackle the question and answer independently, while the proposed structures develop an efficient attentive models to generate answer embeddings according to the question."

  - https://github.com/brmson/dataset-sts/blob/master/models/attn1511.py + https://github.com/brmson/dataset-sts/blob/master/models/rnncnn.py	
  - https://github.com/brmson/dataset-sts/blob/master/models/cnnrnn.py


#### Santos, Tan, Xiang, Zhou - ["Attentive Pooling Networks"](http://arxiv.org/abs/1602.03609) (IBM Watson)
>	"In this work, we propose Attentive Pooling, a two-way attention mechanism for discriminative model training. In the context of pair-wise ranking or classification with neural networks, AP enables the pooling layer to be aware of the current input pair, in a way that information from the two input items can directly influence the computation of each other’s representations. Along with such representations of the paired inputs, AP jointly learns a similarity measure over projected segments (e.g. trigrams) of the pair, and subsequently, derives the corresponding attention vector for each input to guide the pooling. Our two-way attention mechanism is a general framework independent of the underlying representation learning, and it has been applied to both convolutional neural networks and recurrent neural networks in our studies. The empirical results, from three very different benchmark tasks of question answering/answer selection, demonstrate that our proposed models outperform a variety of strong baselines and achieve state-of-the-art performance in all the benchmarks."

>	"The key contribution of this work is that we propose Attentive Pooling, a two-way attention mechanism, that significantly improves such discriminative models’ performance on pair-wise ranking or classification, by enabling a joint learning of the representations of both inputs as well as their similarity measurement. Specifically, AP enables the pooling layer to be aware of the current input pair, in a way that information from the two input items can directly influence the computation of each other’s representations. The main idea in AP consists of learning a similarity measure over projected segments (e.g. trigrams) of the two items in the input pair, and using the similarity scores between the segments to compute attention vectors in both directions. Next, the attention vectors are used to perform pooling."

>	"There are a few key benefits of our model.
>	 - Thanks to the two-way attention, our model projects the paired inputs, even though they may not be always semantically comparable for some applications (e.g., questions and answers in question answering), into a common representation space that they can be compared in a more plausible way.
>	 - Our model is effective in matching pairs of inputs with significant length variations.
>	 - The two-way attention mechanism is independent of the underlying representation learning. For example, AP can be applied to both CNNs and RNNs, which is in contrast to the one-way attention used in the generation models mostly based on recurrent nets."
>	"(1) Attentive Pooling is more general than recently proposed two-way attention mechanism because: (a) it learns how to compute interactions between the items in the input pair; and (b) it can be applied to both CNNs and RNNs; (2) we demonstrate that AP can be effectively used with CNNs and biLSTM in the context of the answer selection task, using three different benchmark datasets; (3) our experimental results demonstrate that AP helps the CNN to cope with large input texts; (4) we present new state-of-theart results for InsuranceQA and TREC-QA datasets. (5) for the WikiQA dataset our results are the best reported so far for methods that do not use handcrafted features."


#### Severyn, Moschitti - ["Learning to Rank Short Text Pairs with Convolutional Deep Neural Networks"](http://disi.unitn.it/~severyn/papers/sigir-2015-long.pdf)
>	"Learning a similarity function between pairs of objects is at the core of learning to rank approaches. In information retrieval tasks we typically deal with query-document pairs, in question answering - question-answer pairs. However, before learning can take place, such pairs needs to be mapped from the original space of symbolic words into some feature space encoding various aspects of their relatedness, e.g. lexical, syntactic and semantic. Feature engineering is often a laborious task and may require external knowledge sources that are not always available or difficult to obtain. Recently, deep learning approaches have gained a lot of attention from the research community and industry for their ability to automatically learn optimal feature representation for a given task, while claiming state-of-the-art performance in many tasks in computer vision, speech recognition and natural language processing. In this paper, we present a convolutional neural network architecture for reranking pairs of short texts, where we learn the optimal representation of text pairs and a similarity function to relate them in a supervised way from the available training data. Our network takes only words in the input, thus requiring minimal preprocessing. In particular, we consider the task of reranking short text pairs where elements of the pair are sentences. We test our deep learning system on two popular retrieval tasks from TREC: Question Answering and Microblog Retrieval. Our model demonstrates strong performance on the first task beating previous state-of-the-art systems by about 3% absolute points in both MAP and MRR and shows comparable results on tweet reranking, while enjoying the benefits of no manual feature engineering and no additional syntactic parsers."

>	"In this paper, we propose a novel deep learning architecture for reranking short texts. It has the benefits of requiring no manual feature engineering or external resources, which may be expensive or not available. The model with the same architecture can be successfully applied to other domains and tasks. Our experimental findings show that our deep learning model: (i) greatly improves on the previous state-of-the-art systems and a recent deep learning approach in on answer sentence selection task showing a 3% absolute improvement in MAP and MRR; (ii) our system is able to improve even the best system runs from TREC Microblog 2012 challenge; (iii) is comparable to the syntactic reranker, while our system requires no external parsers or resources."


#### Baudis, Sedivy - ["Sentence Pair Scoring: Towards Unified Framework for Text Comprehension"](http://arxiv.org/abs/1603.06127)
>	"We review the task of Sentence Pair Scoring, popular in the literature in various forms - slanted as Answer Sentence Selection, Paraphrasing, Semantic Text Scoring, Next Utterance Ranking, Recognizing Textual Entailment or e.g. a component of Memory Networks. We argue that all such tasks are similar from the model perspective and propose new baselines by comparing the performance of common IR metrics and popular convolutional, recurrent and attention-based neural models across many Sentence Pair Scoring tasks and datasets. We discuss the problem of evaluating randomized models, propose a statistically grounded methodology, and attempt to improve comparisons by releasing new datasets that are much harder than some of the currently used well explored benchmarks. To address the current research fragmentation in a future-proof way, we introduce a unified open source software framework with easily pluggable models and tasks, allowing easy evaluation of sentence models on a wide range of semantic natural language datasets. This allows us to outline a path towards a universal learned semantic model for machine reading tasks. We support this plan by experiments that demonstrate reusability of trained sentence models across tasks and corpora of very different nature."

>	"We have unified a variety of tasks in a single scientific framework of sentence pair scoring, and demonstrated a platform for general modelling of this problem and aggregate benchmarking of these models across many datasets. Promising initial transfer learning results suggest that a quest for generic neural model capable of task-independent text comprehension is becoming a meaningful pursuit. The open source nature of our framework and the implementation choice of a popular and extensible deep learning library allows for high reusability of our research and easy extensions with further more advanced models."

>	"Based on our benchmarks, as a primary model for applications on new f2-type tasks, we can recommend either the RNN-CNN model or transfer learning based on the Ubu. RNN model."

  - https://github.com/brmson/dataset-sts


#### Iyyer, Manjunatha, Boyd-Graber, Daume - ["Deep Unordered Composition Rivals Syntactic Methods for Text Classification"](http://cs.umd.edu/~miyyer/pubs/2015_acl_dan.pdf)
>	"Many existing deep learning models for natural language processing tasks focus on learning the compositionality of their inputs, which requires many expensive computations. We present a simple deep neural network that competes with and, in some cases, outperforms such models on sentiment analysis and factoid question answering tasks while taking only a fraction of the training time. While our model is syntactically-ignorant, we show significant improvements over previous bag-of-words models by deepening our network and applying a novel variant of dropout. Moreover, our model performs better than syntactic models on datasets with high syntactic variance. We show that our model makes similar errors to syntactically-aware models, indicating that for the tasks we consider, nonlinearly transforming the input is more important than tailoring a network to incorporate word order and syntax."

>	"In this paper, we introduce the deep averaging network, which feeds an unweighted average of word vectors through multiple hidden layers before classification. The DAN performs competitively with more complicated neural networks that explicitly model semantic and syntactic compositionality. It is further strengthened by word dropout, a regularizer that reduces input redundancy. DANs obtain close to state-of-the-art accuracy on both sentence and document-level sentiment analysis and factoid question-answering tasks with much less training time than competing methods; in fact, all experiments were performed in a matter of minutes on a single laptop core. We find that both DANs and syntactic functions make similar errors given syntactically-complex input, which motivates research into more powerful models of compositionality."

>	"Theoretically, word dropout can also be applied to other neural network-based approaches. However, we observe no significant performance differences in preliminary experiments when applying word dropout to leaf nodes in RecNNs for sentiment analysis (dropped leaf representations are set to zero vectors), and it slightly hurts performance on the question answering task."

>	"We compare DANs to both the shallow NBOW model as well as more complicated syntactic models on sentence and document-level sentiment analysis and factoid question answering tasks. Our results show that DANs outperform other bag-ofwords models and many syntactic models with very little training time. On the question-answering task, DANs effectively train on out-of-domain data, while RecNNs struggle to reconcile the syntactic differences between the training and test data."

  - http://youtube.com/watch?v=y1_0i1RF74c (Iyyer)
  - https://cs.umd.edu/~miyyer/data/acldan_slides.pdf
  - http://github.com/miyyer/dan


#### Wieting, Bansal, Gimpel, Livescu - ["Towards Universal Paraphrastic Sentence Embeddings"](http://arxiv.org/abs/1511.08198)
>	"We consider the problem of learning general-purpose, paraphrastic sentence embeddings based on supervision from the Paraphrase Database. We compare six compositional architectures, evaluating them on annotated textual similarity datasets drawn both from the same distribution as the training data and from a wide range of other domains. We find that the most complex architectures, such as long short-term memory (LSTM) recurrent neural networks, perform best on the in-domain data. However, in out-of-domain scenarios, simple architectures such as word averaging vastly outperform LSTMs. Our simplest averaging model is even competitive with systems tuned for the particular tasks while also being extremely efficient and easy to use. In order to better understand how these architectures compare, we conduct further experiments on three supervised NLP tasks: sentence similarity, entailment, and sentiment classification. We again find that the word averaging models perform well for sentence similarity and entailment, outperforming LSTMs. However, on sentiment classification, we find that the LSTM performs very strongly - even recording new state-of-the-art performance on the Stanford Sentiment Treebank. We then demonstrate how to combine our pretrained sentence embeddings with these supervised tasks, using them both as a prior and as a black box feature extractor. This leads to performance rivaling the state of the art on the SICK similarity and entailment tasks. We release all of our resources to the research community 1 with the hope that they can serve as the new baseline for further work on universal sentence embeddings."

  - http://videolectures.net/iclr2016_wieting_universal_paraphrastic/ (Wieting)
  - https://github.com/jwieting/iclr2016


#### Iyyer, Boyd-Graber, Claudino, Socher, Daume - ["A Neural Network for Factoid Question Answering over Paragraphs"](http://cs.umd.edu/~miyyer/qblearn/)
>	"We introduce a recursive neural network model that is able to correctly answer paragraph-length factoid questions from a trivia competition called quiz bowl. Text classification methods for tasks like factoid question answering typically use manually defined string matching rules or bag of words representations. Our model is able to succeed where traditional approaches fail, particularly when questions contain very few words (e.g., named entities) indicative of the answer. We introduce a recursive neural network model that can reason over such input by modeling textual compositionality. Unlike previous RNN models, our model QANTA learns word and phrase-level representations that combine across sentences to reason about entities. The model outperforms multiple baselines and, when combined with information retrieval methods, rivals the best human players."

>	"We use a specially designed dataset that challenges humans: a trivia game called Quiz bowl. These questions are written so that they can be interrupted by someone who knows more about the answer; that is, harder clues are at the start of the question and easier clues are at the end of the question. The content model produces guesses of what the answer could be and the policy must decide when to accept the guess.
Quiz bowl is a fun game with excellent opportunities for outreach, but it is also related to core challenges in natural language processing: classification (sorting inputs and making predictions), discourse (using pragmatic clues to guess what will come next), and coreference resolution (knowing which entities are discussed from oblique mentions)."

>	"Why not traditional QA? Information Retrieval systems work by querying some large knowledge base for terms similar to those in the query. But what if the query lacks informative terms? In such cases, we have to model the compositionality of the query. A dependency-tree recursive neural network model, QANTA, that computes distributed question representations to predict answers. QANTA outperforms multiple strong baselines and defeats human quiz bowl players when combined with IR methods."

  - http://youtube.com/watch?v=LqsUaprYMOw + http://youtube.com/watch?v=-jbqiXvmY9w (exhibition game against team of Jeopardy champions)
  - http://youtube.com/watch?v=kTXJCEvCDYk + https://goo.gl/ZcQB6n (exhibition game against Ken Jennings)
  - http://youtube.com/watch?v=c2kGD1EdfFw (exhibition game against Quiz Bowl champions)
  - http://youtube.com/watch?v=bQHo7BApgAU&t=5m48s (game against California NASAT team)
  - http://youtube.com/watch?v=ZVHR8OAHDlI (Boyd-Graber, Iyyer)
  - http://youtube.com/watch?v=ZRYObdTOaEI (Iyyer)
  - http://youtube.com/watch?v=YArUk9QcMe0 (Boyd-Graber)
  - http://youtu.be/tdLmf8t4oqM?t=27m25s (Socher)
  - http://youtu.be/BVbQRrrsJo0?t=34m30s (Socher)
  - http://videolectures.net/deeplearning2015_socher_nlp_applications/ (Socher, 09:00)
  - http://youtu.be/9RAo50pVDGI?t=33m20s (Daume)
  - http://emnlp2014.org/material/poster-EMNLP2014070.pdf (technical overview)
  - https://github.com/miyyer/qb + http://cs.umd.edu/~miyyer/qblearn/qanta.tar.gz + https://github.com/jcoreyes/NLQA/tree/master/qanta
  - http://cs.colorado.edu/~jbg/projects/IIS-1320538.html
  - http://hsquizbowl.org/forums/viewtopic.php?f=2&t=17364#p303823


#### Nogueira, Cho - ["End-to-End Goal-Driven Web Navigation"](http://arxiv.org/pdf/1602.02261)
>	"We propose a goal-driven web navigation as a benchmark task for evaluating an agent with abilities to understand natural language and plan on partially observed environments. In this challenging task, an agent navigates through a website, which is represented as a graph consisting of web pages as nodes and hyperlinks as directed edges, to find a web page in which a query appears. The agent is required to have sophisticated high-level reasoning based on natural languages and efficient sequential decision-making capability to succeed. We release a software tool, called WebNav, that automatically transforms a website into this goal-driven web navigation task, and as an example, we make WikiNav, a dataset constructed from the English Wikipedia. We extensively evaluate different variants of neural net based artificial agents on WikiNav and observe that the proposed goal-driven web navigation well reflects the advances in models, making it a suitable benchmark for evaluating future progress. Furthermore, we extend the WikiNav with questionanswer pairs from Jeopardy! and test the proposed agent based on recurrent neural networks against strong inverted index based search engines. The artificial agents trained on WikiNav outperforms the engined based approaches, demonstrating the capability of the proposed goal-driven navigation as a good proxy for measuring the progress in real-world tasks such as focused crawling and question-answering."

>	"In this work, we describe a large-scale goal-driven web navigation task and argue that it serves as a useful test bed for evaluating the capabilities of artificial agents on natural language understanding and planning. We release a software tool, called WebNav, that compiles a given website into a goal-driven web navigation task. As an example, we construct WikiNav from Wikipedia using WebNav. We extend WikiNav with Jeopardy! questions, thus creating WikiNav-Jeopardy. We evaluate various neural net based agents on WikiNav and WikiNav-Jeopardy. Our results show that more sophisticated agents have better performance, thus supporting our claim that this task is well suited to evaluate future progress in natural language understanding and planning. Furthermore, we show that our agent pretrained on WikiNav outperforms two strong inverted-index based search engines on the WikiNav-Jeopardy. These empirical results support our claim on the usefulness of the proposed task and agents in challenging applications such as focused crawling and question-answering."

  - Value Iteration Networks for this problem [https://arxiv.org/abs/1602.02867] - https://youtu.be/tXBHfbHHlKc?t=31m20s (Tamar)


#### Bordes, Usunier, Chopra, Weston - ["Large-scale Simple Question Answering with Memory Networks"](http://arxiv.org/abs/1506.02075)
>	"Training large-scale question answering systems is complicated because training sources usually cover a small portion of the range of possible questions. This paper studies the impact of multitask and transfer learning for simple question answering; a setting for which the reasoning required to answer is quite easy, as long as one can retrieve the correct evidence given a question, which can be difficult in large-scale conditions. To this end, we introduce a new dataset of 100k questions that we use in conjunction with existing benchmarks. We conduct our study within the framework of Memory Networks because this perspective allows us to eventually scale up to more complex reasoning, and show that Memory Networks can be successfully trained to achieve excellent performance."

>	"The best published competing approach (Yang et al., 2014) has an F1-score of 41.3%, which is comparable to a single run of our model (41.2%). On the new SimpleQuestions dataset, the best models achieve 62 - 63% accuracy, while the supporting fact is in the candidate set for about 86% of SimpleQuestions questions. This shows that MemNNs are effective at re-ranking the candidates, but also that simple QA is still not solved."

>	"First, the removal of the mediator nodes allows us to restrict ourselves to single supporting facts, while they search in paths of length 2 with a heuristic to select the paths to follow (otherwise, inference is too costly), which makes our inference simpler and more efficient. Second, using grouped facts, we integrate multiple answers during learning (through the distant supervision), while they use a grouping heuristic at test time. Grouping facts also allows us to scale much better and to train on FB5M. On WebQuestions, not specifically designed as a simple QA dataset, 86% of the questions can now be answered with a single supporting fact, and performance increases significantly (from 36.2% to 41.0% F1-score)."

>	"This paper presents an implementation of MemNNs for the task of large-scale simple QA. Our results demonstrate that, if properly trained, MemNNs are able to handle natural language and a very large memory (millions of entries), and hence can reach state-of-the-art on the popular benchmark WebQuestions. We want to emphasize that many of our findings, especially those regarding how to format the KB, do not only concern MemNNs but potentially any QA system. This paper also introduced the new dataset SimpleQuestions, which, with 100k examples, is one order of magnitude bigger than WebQuestions: we hope that it will foster interesting new research in QA, simple or not."

##
>	"questions/challenges for large-scale q&a:
>	 - require more training data (hard to generalize to unknown types of questions)
>	 - still quite some engineering (indexing)
>	 - hashing/string matching is not learned"

  - http://youtu.be/jRkm6PXRVF8?t=34m58s (Weston)
  - http://youtu.be/8keqd1ewsno?t=18m48s (Bordes)


#### Ture, Jojic - ["Simple and Effective Question Answering with Recurrent Neural Networks"](http://arxiv.org/abs/1606.05029)
>	"First-order factoid question answering assumes that the question can be answered by a single fact in a knowledge base. While this does not seem like a challenging task, many recent attempts that apply either complex linguistic reasoning or deep neural networks achieve 35%–65% accuracy on benchmark sets. Our approach formulates the task as two machine learning problems: detecting the entities in the question, and classifying the question as one of the relation types in the KB. Based on this assumption of the structure, our simple yet effective approach trains two recurrent neural networks to outperform state of the art by significant margins - relative improvement reaches 16% for WebQuestions, and surpasses 38% for SimpleQuestions."

>	"We described a simple yet effective approach for factoid question answering. We assume that first-order QA can be reduced to two tasks, entity detection and relation prediction, and provide solutions to each with a recurrent neural network. Experimental results indicate impressive improvements over the state of the art on two commonly-used QA benchmark datasets: relative improvements in accuracy were 15.7% for WQ and 38.2% for SQ. From these very positive results, we can deduce that RNNs are very effective at tagging and classification over arbitrary text sequences. We can also argue that building a specific architecture that custom-fits the task has advantages over architectures aiming to do more general-purpose reasoning over text (e.g., (Bordes et al., 2015; Kumar et al., 2015)). Our approach would require a non-trivial augmentation to work with other types of QA tasks: “What movie did both Tom Hanks and Meg Ryan appear in?” requires us to find an entity in the KB that is related to the two entities in the question. Finally, we found that many mistakes are due to search-related issues, so a more refined retrieval could improve accuracy."


#### Weston, Chopra, Bordes - ["Memory Networks"](http://arxiv.org/abs/1410.3916)
>	"We describe a new class of learning models called memory networks. Memory networks reason with inference components combined with a long-term memory component; they learn how to use these jointly. The long-term memory can be read and written to, with the goal of using it for prediction. We investigate these models in the context of question answering where the long-term memory effectively acts as a (dynamic) knowledge base, and the output is a textual response. We evaluate them on a large-scale QA task, and a smaller, but more complex, toy task generated from a simulated world. In the latter, we show the reasoning power of such models by chaining multiple supporting sentences to answer questions that require understanding the intension of verbs."

  - https://facebook.com/video.php?v=10153098860532200 (demo)
  - http://youtube.com/watch?v=Xumy3Yjq4zk + http://cs224d.stanford.edu/lectures/CS224d-Lecture12.pdf (Weston)
  - http://techtalks.tv/talks/memory-networks-for-language-understanding/62356/ (Weston)
  - http://youtu.be/jRkm6PXRVF8?t=16m29s (Weston)
  - http://blog.acolyer.org/2016/03/10/memory-networks/
  - https://docs.google.com/file/d/0B_hicYJxvbiOT3QyTm4wdHlaeWs
  - https://reddit.com/r/MachineLearning/comments/2xcyrl/i_am_j%C3%BCrgen_schmidhuber_ama/cp4ecce
  - https://github.com/fchollet/keras/blob/master/examples/babi_memnn.py


#### Sukhbaatar, Szlam, Weston, Fergus - ["End-To-End Memory Networks"](http://arxiv.org/abs/1503.08895)
>	"We introduce a neural network with a recurrent attention model over a possibly large external memory. The architecture is a form of Memory Network but unlike the model in that work, it is trained end-to-end, and hence requires significantly less supervision during training, making it more generally applicable in realistic settings. It can also be seen as an extension of RNNsearch to the case where multiple computational steps (hops) are performed per output symbol. The flexibility of the model allows us to apply it to tasks as diverse as (synthetic) question answering and to language modeling. For the former our approach is competitive with Memory Networks, but with less supervision. For the latter, on the Penn TreeBank and Text8 datasets our approach demonstrates slightly better performance than RNNs and LSTMs. In both cases we show that the key concept of multiple computational hops yields improved results."

>	"In this work we showed that a neural network with an explicit memory and a recurrent attention mechanism for reading the memory can be sucessfully trained via backpropagation on diverse tasks from question answering to language modeling. Compared to the Memory Network implementation there is no supervision of supporting facts and so our model can be used in more realistic QA settings. Our model approaches the same performance of that model, and is significantly better than other baselines with the same level of supervision. On language modeling tasks, it slightly outperforms tuned RNNs and LSTMs of comparable complexity. On both tasks we can see that increasing the number of memory hops improves performance. However, there is still much to do. Our model is still unable to exactly match the performance of the memory networks trained with strong supervision, and both fail on several of the QA tasks. Furthermore, smooth lookups may not scale well to the case where a larger memory is required. For these settings, we plan to explore multiscale notions of attention or hashing."

  - http://research.microsoft.com/apps/video/default.aspx?id=259920 (Sukhbaatar)
  - http://youtube.com/watch?v=8keqd1ewsno (Bordes)
  - http://www.shortscience.org/paper?bibtexKey=conf/nips/SukhbaatarSWF15
  - https://github.com/facebook/MemNN
  - https://github.com/vinhkhuc/MemN2N-babi-python
  - https://github.com/fchollet/keras/blob/master/examples/babi_memnn.py
  - https://github.com/domluna/memn2n
  - https://github.com/carpedm20/MemN2N-tensorflow
  - https://github.com/npow/MemNN


#### Miller, Fisch, Dodge, Karimi, Bordes, Weston - ["Key-Value Memory Networks for Directly Reading Documents"](https://arxiv.org/abs/1606.03126)
>	"Directly reading documents and being able to answer questions from them is a key problem. To avoid its inherent difficulty, question answering has been directed towards using Knowledge Bases instead, which has proven effective. Unfortunately KBs suffer from often being too restrictive, as the schema cannot support certain types of answers, and too sparse, e.g. Wikipedia contains much more information than Freebase. In this work we introduce a new method, Key-Value Memory Networks, that makes reading documents more viable by utilizing different encodings in the addressing and output stages of the memory read operation. To compare using KBs, information extraction or Wikipedia documents directly in a single framework we construct an analysis tool, MOVIEQA, a QA dataset in the domain of movies. Our method closes the gap between all three settings. It also achieves state-of-the-art results on the existing WIKIQA benchmark."

>	"We studied the problem of directly reading documents in order to answer questions, concentrating our analysis on the gap between such direct methods and using human-annotated or automatically constructed KBs. We presented a new model, Key-Value Memory Networks, which helps bridge this gap, outperforming several other methods across two datasets, MOVIEQA and WIKIQA. However, some gap in performance still remains. MOVIEQA serves as an analysis tool to shed some light on the causes. Future work should try to close this gap further. Key-Value Memory Networks are a versatile tool for reading documents or KBs and answering questions about them - allowing to encode prior knowledge about the task at hand in the key and value memories. These models could be applied to storing and reading memories for other tasks as well, and future work should try them in other domains, such as in a full dialog setting."

  - https://gist.github.com/shagunsodhani/a5e0baa075b4a917c0a69edc575772a8


#### Kumar, Irsoy, Su, Bradbury, English, Pierce, Ondruska, Gulrajani, Socher - ["Ask Me Anything: Dynamic Memory Networks for Natural Language Processing"](http://arxiv.org/abs/1506.07285)
>	"Most tasks in natural language processing can be cast into question answering problems over language input. We introduce the dynamic memory network, a unified neural network framework which processes input sequences and questions, forms semantic and episodic memories, and generates relevant answers. Questions trigger an iterative attention process which allows the model to condition its attention on the result of previous iterations. These results are then reasoned over in a hierarchical recurrent sequence model to generate answers. The DMN can be trained end-to-end and obtains state of the art results on several types of tasks and datasets: question answering (Facebook’s bAbI dataset), sequence modeling for part of speech tagging (WSJ-PTB), and text classification for sentiment analysis (Stanford Sentiment Treebank). The model relies exclusively on trained word vector representations and requires no string matching or manually engineered features."

>	"Question answering is a complex natural language processing task which requires an understanding of the meaning of a text and the ability to reason over relevant facts. Most, if not all, tasks in natural language processing can be cast as a question answering problem: high level tasks like machine translation ("What is the translation into French?"); sequence modeling tasks like named entity recognition ("What are the named entity tags in this sentence?") or part of speech tagging ("What are the part of speech tags?"); classification problems like sentiment analysis ("What is the sentiment?"); even multi-sentence joint classification problems like coreference resolution ("Who does 'their' refer to?"). The dynamic memory network is a neural network based model which can be trained in an end-to-end fashion for any QA task using raw input-question-answer triplets. Generally, DMN can solve sequence tagging tasks, classification problems, sequence to sequence tasks, and question answering tasks that require transitive reasoning. The DMN first processes all input, question and answer texts into sequences of semantic vector representations. The question representation triggers an iterative attention process that searches the input and retrieves relevant facts. The DMN then reasons over retrieved facts and provides an answer sequence model with an appropriate summary."

>	"Input Module: This module processes raw inputs and maps them to a representation that is useful for asking questions about this input. The input may be, for instance, an image, video, or audio signal. We focus on NLP in this paper. Hence, the input may be a sentence, a long story, a movie review, a news article, or all of Wikipedia."

>	"Semantic Memory Module: Semantic memory stores general knowledge about concepts and facts. For example, it might contain information about what a hang glider is. Initialization strategies such as distributed word vectors are popular semantic memory components that have been shown to improve performance on many NLP tasks. More complex information can be stored in the form of knowledge bases that capture relationships in the form of triplets or gazetteers, which have been useful for tasks such as named entity recognition or question answering."

>	"Question Module: The question module computes a representation of a question such as "Where did the author first fly?". This representation triggers the episodic memory module to start an iterative attention process over facts from the input sequence."

>	"Episodic Memory Module: This is the central part of the DMN. A question draws attention to specific facts from the input sequence, which are reasoned over to update this module’s memory state. This process then iterates, with each iteration providing the module with newly relevant information about the input. In other words, the module has the ability to retrieve new facts which were thought to be irrelevant in previous iterations. After several passes the module then summarizes its knowledge and provides the answer module with a final representation to produce an answer. The episodic memory module retrieves facts from the input module conditioned on the question. It then reasons over those facts to produce a final representation that the answer module will use to generate an answer. We refer to this representation as a memory. Importantly, we allow our module to take multiple passes over the facts, focusing attention on different facts at each pass. Each pass produces an episode, and these episodes are then summarized into the memory. Endowing our module with this episodic component allows its attention mechanism to attend more selectively to specific facts on each pass, as it can attend to other important facts at a later pass. It also allows for a type of transitive inference, since the first pass may uncover the need to retrieve additional facts. For instance, we are asked "Where is the football?" In the first iteration, the model ought attend to sentence "John put down the football", as the question asks about the football. Only once the model sees that John is relevant can it reason the second iteration should retrieve where John was. In its general form, the episodic memory module is characterized by an attention mechanism, a function which returns an episode given the output of the attention mechanism and the facts from the input module, and a function that summarizes the episodes into a memory."

>	"Answer Module: Given a representation from the episodic memory module, the answer module generates the model’s predicted answer."

>	"Training is cast as a supervised classification problem to minimize cross entropy error of the answer sequence. For datasets with gate supervision, such as bAbI, we also include the cross entropy error of the gates into the overall cost. Because all modules communicate over vector representations and various types of differentiable and deep neural networks with gates, the entire DMN model can be trained via backpropagation and gradient descent."

>	"There are several deep learning models that have been applied to many different tasks in NLP. For instance, recursive neural networks have been used for parsing, sentiment analysis, paraphrase detection, question answering and logical inference, among other tasks. However, because they lack the memory and question modules, a single model cannot solve as many varied tasks, nor tasks that require transitive reasoning over multiple sentences."

>	"Memory Networks model cannot be applied to the same variety of NLP tasks (unlike Dynamic Memory Networks model) since it processes sentences independently and not via a sequence model. It requires bag of n-gram string matching features as well as a separate feature that captures whether a sentence came before another one. The DMN does worse than the MemNN on tasks with long input sequences. We suspect this is due to the recurrent input sequence model having trouble modeling very long inputs. The MemNN does not suffer from this problem as it views each sentence seperately. The power of the episodic memory module is evident in tasks which require the model to iteratively retrieve facts and store them in a representation that slowly incorporates more of the relevant information of the input sequence."

>	"We believe the DMN is a potentially general model for a variety of NLP applications. The entire model can be trained end-to-end with one, albeit complex, objective function. The model uses some ideas from neuroscience such as semantic and episodic memories known to be required for complex types of reasoning. Future work will explore additional tasks, larger multi-task models and multimodal inputs and questions."

##
>	"The paper proposes an end-to-end differentiable NN module called DMN. It consists of 4 parts, an input module, question module, episodic memory module and an answer module. Their works appear quite similar to the MemNN neural network with the main difference being the episodic memory module, which is an attention based recurrent module over the input hidden states and the question state. The authors argue that in many cases multiple passes over all the facts and question can help in better question answering."

>	"The main modeling idea is that you take a question and use it to condition a neural attention mechanism that goes over some text. The text is represented in terms of hidden states of a bidirectional sequence model. Conditioned on the question, that attention mechanism goes over inputs at each time step, and connects them to an episodic memory module. That is, it opens a gate that lets the vector at a time step be fed into the episodic memory. One important aspect for some tasks is that the model goes over the input multiple times. After each time it classifies the memory state by asking "do I know enough to answer the question?" And if not, then it goes over the input again, but conditioned on the question and also the previous memory state. That way it can reason over multiple facts. Once it classifies "yes I know enough", it gives that memory vector to an output sequence model which generates the answer."

  - http://yerevann.com/dmn-ui/ (demo)
  - http://videolectures.net/deeplearning2015_socher_nlp_applications/ (Socher, 00:42)
  - http://www.iro.umontreal.ca/~memisevr/dlss2015/DLSummerSchoolLecture2.pdf
  - http://yerevann.github.io/2016/02/05/implementing-dynamic-memory-networks/
  - https://napsternxg.gitbooks.io/article-reviews/content/ama_socher.html
  - https://github.com/swstarlab/DynamicMemoryNetworks


#### Seo, Hajishirzi, Farhadi - ["Query-Regression Networks for Machine Comprehension"](http://arxiv.org/abs/1606.04582)
>	"We present Query-Regression Network, a variant of Recurrent Neural Network that is suitable for end-to-end machine comprehension. While previous work largely relied on external memory and attention mechanism, QRN is a single recurrent unit with internal memory. Unlike most RNN-based models, QRN is able to effectively handle long-term dependencies and is highly parallelizable. In our experiments we show that QRN outperforms the state of the art in end-to-end bAbI QA tasks."

>	"Query-Regression Network answers machine comprehension questions by storing local queries and regressing them as QRN observes state-changing sentences. While an RNN-based model, QRN is effective for encoding long-term dependencies between sentences. In addition, it is simpler than previous work [Dynamic Memory Networks] and is highly parallelizable, making them a suitable choice for large-scale question answering when the size of stories grows. Lastly, QRN is able to answer questions after each time step, and its internal representation, in the form of updated query, is interpretable. We have experimentally shown that QRN is capable of learning to perform different kinds of reasoning over multiple facts in bAbI QA dataset. Future work involves using QRN for language modeling and machine comprehension on real data such as MCTest."

>	"The attention mechanism allows the models to focus on a single sentence in each layer, and the models can sequentially read multiple relevant sentences from the memory with multiple layers. However, the biggest drawback of the vanilla attention mechanism is that it is insensitive to the time step (memory address) of the sentences when accessing them. End-to-end Memory Network attempts to resolve this problem by adding time-dependent variable to the sentence representation at each time step (address) of the memory. Dynamic Memory Network combines RNN and attention mechanism together to incorporate time dependency into the model. Our proposed model is a single recurrent unit that addresses the long-term dependency problem of most RNN-based models while taking the full advantage of RNN’s capability to model sequential data. QRN considers the sentences (story) as a sequence of state-changing triggers, and QRN transforms (regresses) the original question (query) to an easierto-answer query as it observes each trigger through time. For instance, the original question, “Where is the apple?” cannot be directly answered by any single sentence from the story. Hence, after observing the first sentence “Sandra got the apple there.”, QRN transforms the original question to “Where is Sandra?”, which is presumably easier to answer. This mechanism is akin to logic regression in situation calculus. While previous work can be also viewed as performing query regression through multiple layers, QRN is distinct from their approaches in that the query regression in our model is performed locally (timewise), so it can better encode locality information. We will experimentally demonstrate that the local query regression is effective for handling the time dependency problem, and we will show that QRN can be parallelized over time, unlike most RNN-based models."

  - https://github.com/seominjoon/qrn


#### Peng, Lu, Li, Wong - ["Towards Neural Network-based Reasoning"](http://arxiv.org/abs/1508.05508)
>	"We propose Neural Reasoner, a framework for neural network-based reasoning over natural language sentences. Given a question, Neural Reasoner can infer over multiple supporting facts and find an answer to the question in specific forms. Neural Reasoner has 1) a specific interaction-pooling mechanism, allowing it to examine multiple facts, and 2) a deep architecture, allowing it to model the complicated logical relations in reasoning tasks. Assuming no particular structure exists in the question and facts, Neural Reasoner is able to accommodate different types of reasoning and different forms of language expressions. Despite the model complexity, Neural Reasoner can still be trained effectively in an end-to-end manner. Our empirical studies show that Neural Reasoner can outperform existing neural reasoning systems with remarkable margins on two difficult artificial tasks (Positional Reasoning and Path Finding) proposed. For example, it improves the accuracy on Path Finding (10K) from 33.4% to over 98%."

>	"We have proposed Neural Reasoner, a framework for neural network-based reasoning over natural language sentences. Neural Reasoner is flexible, powerful, and language indepedent. Our empirical studies show that Neural Reasoner can dramatically improve upon existing neural reasoning systems on two difficult artificial tasks. For future work, we will explore 1) tasks with higher difficulty and reasoning depth, e.g., tasks which require a large number of supporting facts and facts with complex intrinsic structures, 2) the common structure in different but similar reasoning tasks (e.g., multiple tasks all with general questions), and 3) automatic selection of the reasoning architecture, for example, determining when to stop the reasoning based on the data."

##
Weston:
>	"similar to Memory Networks but with non-linear function to compute interaction between control state and memory slot"

  - http://thespermwhale.com/jaseweston/ram/slides/session2/neural-reason.pdf
  - https://www.evernote.com/shard/s189/sh/54f4534f-3813-44de-8feb-af7180eceb8e/953160fcc0f551cb9855d46cf686375b


#### Hermann, Kocisky, Grefenstette, Espeholt, Kay, Suleyman, Blunsom - ["Teaching Machines to Read and Comprehend"](http://arxiv.org/abs/1506.03340)
>	"Teaching machines to read natural language documents remains an elusive challenge. Machine reading systems can be tested on their ability to answer questions posed on the contents of documents that they have seen, but until now large scale training and test datasets have been missing for this type of evaluation. In this work we define a new methodology that resolves this bottleneck and provides large scale supervised reading comprehension data. This allows us to develop a class of attention based deep neural networks that learn to read real documents and answer complex questions with minimal prior knowledge of language structure."

>	"Progress on the path from shallow bag-of-words information retrieval algorithms to machines capable of reading and understanding documents has been slow. Traditional approaches to machine reading and comprehension have been based on either hand engineered grammars, or information extraction methods of detecting predicate argument triples that can later be queried as a relational database. Supervised machine learning approaches have largely been absent from this space due to both the lack of large scale training datasets, and the difficulty in structuring statistical models flexible enough to learn to exploit document structure. While obtaining supervised natural language reading comprehension data has proved difficult, some researchers have explored generating synthetic narratives and queries. Such approaches allow the generation of almost unlimited amounts of supervised data and enable researchers to isolate the performance of their algorithms on individual simulated phenomena. Work on such data has shown that neural network based models hold promise for modelling reading comprehension, something that we will build upon here. Historically, however, many similar approaches in Computational Linguistics have failed to manage the transition from synthetic data to real environments, as such closed worlds inevitably fail to capture the complexity, richness, and noise of natural language. In this work we seek to directly address the lack of real natural language training data by introducing a novel approach to building a supervised reading comprehension data set. We observe that summary and paraphrase sentences, with their associated documents, can be readily converted to context-query-answer triples using simple entity detection and anonymisation algorithms. Using this approach we have collected two new corpora of roughly a million news stories with associated queries from the CNN and Daily Mail websites. We demonstrate the efficacy of our new corpora by building novel deep learning models for reading comprehension. These models draw on recent developments for incorporating attention mechanisms into recurrent neural network architectures. This allows a model to focus on the aspects of a document that it believes will help it answer a question, and also allows us to visualises its inference process. We compare these neural models to a range of baselines and heuristic benchmarks based upon a traditional frame semantic analysis provided by a state-of-the-art natural language processing."

>	"The supervised paradigm for training machine reading and comprehension models provides a promising avenue for making progress on the path to building full natural language understanding systems. We have demonstrated a methodology for obtaining a large number of document-query-answer triples and shown that recurrent and attention based neural networks provide an effective modelling framework for this task. Our analysis indicates that the Attentive and Impatient Readers are able to propagate and integrate semantic information over long distances. In particular we believe that the incorporation of an attention mechanism is the key contributor to these results. The attention mechanism that we have employed is just one instantiation of a very general idea which can be further exploited. However, the incorporation of world knowledge and multi-document queries will also require the development of attention and embedding mechanisms whose complexity to query does not scale linearly with the data set size. There are still many queries requiring complex inference and long range reference resolution that our models are not yet able to answer. As such our data provides a scalable challenge that should support NLP research into the future. Further, significantly bigger training data sets can be acquired using the techniques we have described, undoubtedly allowing us to train more expressive and accurate models."

>	"Summary:
>	 - supervised machine reading is a viable research direction with the available data,
>	 - LSTM based recurrent networks constantly surprise with their ability to encode dependencies in sequences,
>	 - attention is a very effective and flexible modelling technique.
>	Future directions:
>	 - more and better data, corpus querying, and cross document queries,
>	 - recurrent networks incorporating long term and working memory are well suited to NLU task."

##
>	"The model has to be able to detect symbol in the input (answer placeholder in the question) and substitute it with another symbol (word from document).
>	Two strategies for transducing with replacement of answer placeholder symbol with entity symbol: document||query (putting all the information about document into thought vector before knowing the query) or query||document (putting all the information about query before thinking about the answer). The second approach (filtering document after digesting query) works better.
>	We do not tell the model anything about the structure. We don't tell it there are query and document (they are just symbols). We don't tell it there is symbol it has to substitute (it just has to learn them). So there is really long range between variable in query and answer in document (thousands of words). And the problem is more difficult than other transduction problems because of that."

  - http://videolectures.net/deeplearning2015_blunsom_memory_reading/ (Blunsom, 33:00) + http://www.iro.umontreal.ca/~memisevr/dlss2015/num-mr.pdf
  - http://youtu.be/-WPP9f1P-Xc?t=22m28s (Blunsom)
  - http://egrefen.com/docs/HowMuchLinguistics2015.pdf
  - http://www.shortscience.org/paper?bibtexKey=conf/nips/HermannKGEKSB15
  - https://www.evernote.com/shard/s189/sh/ade22da1-4813-4b5c-89a5-3fdf7dbad8ee/ce8b7234b42c62882609047ecc289920
  - https://arxiv.org/abs/1606.02858
  - https://github.com/thomasmesnard/DeepMind-Teaching-Machines-to-Read-and-Comprehend
  - https://github.com/carpedm20/attentive-reader-tensorflow
  - https://github.com/caglar/Attentive_reader/


#### Kadlec, Schmid, Bajgar, Kleindienst - ["Text Understanding with the Attention Sum Reader Network"](http://arxiv.org/abs/1603.01547)
>	"Several large cloze-style context-question-answer datasets have been introduced recently: the CNN and Daily Mail news data and the Children’s Book Test. Thanks to the size of these datasets, the associated text comprehension task is well suited for deep-learning techniques that currently seem to outperform all alternative approaches. We present a new, simple model that uses attention to directly pick the answer from the context as opposed to computing the answer using a blended representation of words in the document as is usual in similar models. This makes the model particularly suitable for question-answering problems where the answer is a single word from the document. Our model outperforms models previously proposed for these tasks by a large margin."

>	"The words from the document and the question are first converted into vector embeddings using a look-up matrix V. The document is then read by a bidirectional GRU network. A concatenation of the hidden states of the forward and backward GRUs at each word is then used as a contextual embedding of this word, intuitively representing the context in which the word is appearing. We can also understand it as representing the set of questions to which this word may be an answer. Similarly the question is read by a bidirectional GRU but in this case only the final hidden states are concatenated to form the question embedding. The attention over each word in the context is then calculated as the dot product of its contextual embedding with the question embedding. This attention is then normalized by the softmax function. While most previous models used this attention as weights to calculate a blended representation of the answer word, we simply sum the attention across all occurrences of each unique words and then simply select the word with the highest sum as the final answer. While simple, this trick seems both to improve accuracy and to speed-up training."


Bajgar, Kadlec, Kleindienst - Embracing data abundance: BookTest Dataset for Reading Comprehension [https://arxiv.org/abs/1610.00956]
>	"There is a practically unlimited amount of natural language data available. Still, recent work in text comprehension has focused on datasets which are small relative to current computing possibilities. This article is making a case for the community to move to larger data and as a step in that direction it is proposing the BookTest, a new dataset similar to the popular Children’s Book Test (CBT), however more than 60 times larger. We show that training on the new data improves the accuracy of our Attention-Sum Reader model on the original CBT test data by a much larger margin than many recent attempts to improve the model architecture. On one version of the dataset our ensemble even exceeds the human baseline provided by Facebook. We then show in our own human study that there is still space for further improvement."

>	"We have shown that simply infusing a model with more data can yield performance improvements of up to 14.8% where several attempts to improve the model architecture on the same training data have given gains of at most 2.1% compared to our best ensemble result."

>	"Since the amount of data is practically unlimited – we could even generate them on the fly resulting in continuous learning similar to the Never-Ending Language Learning by Carnegie Mellon University - it is now the speed of training that determines how much data the model is able to see."

>	"However as we radically increased the dataset size, this would result in an extremely large number of model parameters so we decided to limit the vocabulary size to 200, 000 most frequent words. For each example, each unique out-of-vocabulary word is now mapped on one of 1000 anonymous tokens which are randomly initialized and untrained. Fixing the embeddings of these anonymous tags proved to significantly improve the performance."

>	"If we move model training from joint CBT NE+CN training data to a subset of the BookTest of the same size (230k examples), we see a drop in accuracy of around 10% on the CBT test datasets. Hence even though the Children’s Book Test and BookTest datasets are almost as close as two disjoint datasets can get, the transfer is still very imperfect. This also suggests that the increase in accuracy when using more data that are strictly in the same domain as the original training data results in a performance increase even larger that the one we are reporting on CBT. However the scenario of having to look for additional data elsewhere is more realistic."


#### Sordoni, Bachman, Bengio - ["Iterative Alternating Neural Attention for Machine Reading"](http://arxiv.org/abs/1606.02245)
>	"We propose a novel neural attention architecture to tackle machine comprehension tasks, such as answering Cloze-style queries with respect to a document. Unlike previous models, we do not collapse the query into a single vector, instead we deploy an iterative alternating attention mechanism that allows a fine-grained exploration of both the query and the document. Our model outperforms state-of-the-art baselines in standard machine comprehension benchmarks such as CNN news articles and the Children’s Book Test (CBT) dataset."

>	"We presented an iterative neural attention model and applied it to machine comprehension tasks. Our architecture deploys a novel alternating attention mechanism, and tightly integrates successful ideas from past works in machine reading comprehension to obtain state-of-the-art results on three datasets. The iterative alternating attention mechanism continually refines its view of the query and document while aggregating the information required to answer a query. Multiple future research directions may be envisioned. We plan to dynamically select the optimal number of inference steps required for each example. Moreover, we suspect that shifting towards stochastic attention should permit us to learn more interesting search policies. Finally, we believe that our model is fully general and may be applied in a straightforward way to other tasks such as information retrieval."


#### Yin, Ebert, Schutze - ["Attention-Based Convolutional Neural Network for Machine Comprehension"](http://arxiv.org/abs/1602.04341)
>	"Understanding open-domain text is one of the primary challenges in natural language processing. Machine comprehension benchmarks evaluate the system’s ability to understand text based on the text content only. In this work, we investigate machine comprehension on MCTest, a question answering benchmark. Prior work is mainly based on feature engineering approaches. We come up with a neural network framework, named hierarchical attention-based convolutional neural network (HABCNN), to address this task without any manually designed features. Specifically, we explore HABCNN for this task by two routes, one is through traditional joint modeling of document, question and answer, one is through textual entailment. HABCNN employs an attention mechanism to detect key phrases, key sentences and key snippets that are relevant to answering the question. Experiments show that HABCNN outperforms prior deep learning approaches by a big margin."

>	"This work takes the lead in presenting a CNN based neural network system for open-domain machine comprehension task. Our systems tried to solve this task in a document projection way as well as a textual entailment way. The latter one demonstrates slightly better performance. Overall, our architecture, modeling dynamic document representation by attention scheme from sentence level to snippet level, shows promising results in this task. In the future, more finegrained representation learning approaches are expected to model complex answer types and question types."

  - https://youtube.com/watch?v=N4KklROfLQU


#### Trischler, Ye, Yuan, He, Bachman, Suleman - ["A Parallel-Hierarchical Model for Machine Comprehension on Sparse Data"](http://arxiv.org/abs/1603.08884)
>	"Understanding unstructured text is a major goal within natural language processing. Comprehension tests pose questions based on short text passages to evaluate such understanding. In this work, we investigate machine comprehension on the challenging MCTest benchmark. Partly because of its limited size, prior work on MCTest has focused mainly on engineering better features. We tackle the dataset with a neural approach, harnessing simple neural networks arranged in a parallel hierarchy. The parallel hierarchy enables our model to compare the passage, question, and answer from a variety of trainable perspectives, as opposed to using a manually designed, rigid feature set. Perspectives range from the word level to sentence fragments to sequences of sentences; the networks operate only on word-embedding representations of text. When trained with a methodology designed to help cope with limited training data, our Parallel-Hierarchical model sets a new state of the art for MCTest, outperforming previous feature-engineered approaches slightly and previous neural approaches by a significant margin (over 15% absolute)."

  - https://youtube.com/watch?v=pgVEq7uFRTc + https://youtube.com/watch?v=nbsWpcJASMU + https://youtube.com/watch?v=5UXsPtyBlhs (demo)
  - https://youtube.com/watch?v=qr9Xvka1kEQ (Suleman)
  - https://en.wikipedia.org/wiki/Maluuba#cite_note-8


#### Trischler, Ye, Yuan, Suleman - ["Natural Language Comprehension with the EpiReader"](http://arxiv.org/abs/1606.02270)
>	"We present the EpiReader, a novel model for machine comprehension of text. Machine comprehension of unstructured, real-world text is a major research goal for natural language processing. Current tests of machine comprehension pose questions whose answers can be inferred from some supporting text, and evaluate a model's response to the questions. The EpiReader is an end-to-end neural model comprising two components: the first component proposes a small set of candidate answers after comparing a question to its supporting text, and the second component formulates hypotheses using the proposed candidates and the question, then reranks the hypotheses based on their estimated concordance with the supporting text. We present experiments demonstrating that the EpiReader sets a new state-of-the-art on the CNN and Children's Book Test machine comprehension benchmarks, outperforming previous neural models by a significant margin."

>	"In this article we presented the novel EpiReader framework for machine comprehension, and evaluated it on two large, complex datasets: CNN and CBT. Our model achieves state-of-the-art results on these corpora, outperforming all previous approaches. In future work, we plan to augment our framework with a more powerful model for natural language inference, and explore the effect of pretraining such a model specifically on an inference task. We also plan to try simplifying the model by reusing the Extractor’s biGRU encodings in the Reasoner."

  - https://youtube.com/watch?v=QUwsAPO15_U (demo)


#### Berant, Srikumar, Chen, Huang, Manning, Linden, Harding, Clark - ["Modeling Biological Processes for Reading Comprehension"](http://nlp.stanford.edu/pubs/berant-srikumar-manning-emnlp14.pdf)
>	"Machine reading calls for programs that read and understand text, but most current work only attempts to extract facts from redundant web-scale corpora. In this paper, we focus on a new reading comprehension task that requires complex reasoning over a single document. The input is a paragraph describing a biological process, and the goal is to answer questions that require an understanding of the relations between entities and events in the process. To answer the questions, we first predict a rich structure representing the process in the paragraph. Then, we map the question to a formal query, which is executed against the predicted structure. We demonstrate that answering questions via predicted structures substantially improves accuracy over baselines that use shallower representations."

  - http://youtube.com/watch?v=6tfJZTqPOdg
  - http://youtube.com/watch?v=cGvfkAALb4s


Liang - "Asking Deep Questions on Messy Data"
>	"Knowledge bases, by virtue of their structure, allow one to easily aggregate and filter information. This allows us to ask deep questions using natural language on them thanks to recent advances in semantic parsing. Unfortunately, most knowledge is actually not in a knowledge base, and information extraction, despite best efforts, is still far from obtaining adequate coverage. I will discuss a new generation of semantic parsers that query semi-structured data on web pages directly. The parser jointly reasons over the uncertainty in language and the messiness of the web, answering a new class of questions which was not possible before."

  - https://docs.google.com/file/d/0B_hicYJxvbiOMUJsZGpqUF9NRGM



---
### interesting papers - reasoning

[selected papers](https://dropbox.com/sh/ju4oi0221zo3ql7/AAC8SscYIxR5uk3CVhQXpkuda)


#### Tamar, Wu, Thomas, Levine, Abbeel - ["Value Iteration Networks"](http://arxiv.org/abs/1602.02867)
>	"We introduce the value iteration network (VIN): a fully differentiable neural network with a ‘planning module’ embedded within. VINs can learn to plan, and are suitable for predicting outcomes that involve planning-based reasoning, such as policies for reinforcement learning. Key to our approach is a novel differentiable approximation of the value-iteration algorithm, which can be represented as a convolutional neural network, and trained end-to-end using standard backpropagation. We evaluate VIN based policies on discrete and continuous path-planning domains, and on a natural-language based search task. We show that by learning an explicit planning computation, VIN policies generalize better to new, unseen domains."

>	"The introduction of powerful and scalable RL methods has opened up a range of new problems for deep learning. However, few recent works investigate policy architectures that are specifically tailored for planning under uncertainty, and current RL theory and benchmarks rarely investigate the generalization properties of a trained policy. This work takes a step in this direction, by exploring better generalizing policy representations. Our VIN policies learn an approximate planning computation relevant for solving the task, and we have shown that such a computation leads to better generalization in a diverse set of tasks, ranging from simple gridworlds that are amenable to value iteration, to continuous control, and even to navigation of Wikipedia links. In future work we intend to learn different planning computations, based on simulation, or optimal linear control, and combine them with reactive policies, to potentially develop RL solutions for task and motion planning"

>	"In our experiment in continuous control we used hierarchical policy: high-level policy solved low-resolution map and low-level policy executed it. This is very different from options/skills framework. There is one smooth policy that implements everything. We don't need to learn initiation sets or termination sets. But more importantly, the motivation for using hierarchy here was different. The motivation wasn't to increase learning rate or exploration - the motivation was to generalize. We understood that low-resolution map is sufficient for doing planning which promotes generalization, but low-level policy uses the fact that dynamics is similar across different tasks."

##
>	"Its contribution is to offer a new way to think about value iteration in the context of deep networks. It shows how the CNN architecture can be hijacked to implement the Bellman optimality operator, and how the backprop signal can be used to learn a deterministic model of the underlying MDP."

>	"Value iteration is similar enough to a sequence of convolutions and max-pooling layers that you can emulate an (unrolled) planning computation with a deep network. This allows neural nets to do planning, e.g. moving from start to goal in grid-world, or navigating a website to find query."

  - https://youtube.com/watch?v=tXBHfbHHlKc (Tamar) + http://technion.ac.il/~danielm/icml_slides/Talk7.pdf
  - https://channel9.msdn.com/Events/Neural-Information-Processing-Systems-Conference/Neural-Information-Processing-Systems-Conference-NIPS-2016/Value-Iteration-Networks (Tamar)
  - https://github.com/karpathy/paper-notes/blob/master/vin.md
  - https://github.com/avivt/VIN
  - https://github.com/TheAbhiKumar/tensorflow-value-iteration-networks


#### Pasupat, Liang - ["Compositional Semantic Parsing on Semi-Structured Tables"](http://cs.stanford.edu/~ppasupat/resource/ACL2015-paper.pdf) (reasoning over knowledge base)
>	"Two important aspects of semantic parsing for question answering are the breadth of the knowledge source and the depth of logical compositionality. While existing work trades off one aspect for another, this paper simultaneously makes progress on both fronts through a new task: answering complex questions on semi-structured tables using question-answer pairs as supervision. The central challenge arises from two compounding factors: the broader domain results in an open-ended set of relations, and the deeper compositionality results in a combinatorial explosion in the space of logical forms. We propose a logical-form driven parsing algorithm guided by strong typing constraints and show that it obtains significant improvements over natural baselines. For evaluation, we created a new dataset of 22,033 complex questions on Wikipedia tables, which is made publicly available."

  - http://nlp.stanford.edu/blog/wikitablequestions-a-complex-real-world-question-understanding-dataset/


#### Neelakantan, Le, Sutskever - ["Neural Programmer: Inducing Latent Programs with Gradient Descent"](http://arxiv.org/abs/1511.04834) (neural reasoning over knowledge base)
>	"Deep neural networks have achieved impressive supervised classification performance in many tasks including image recognition, speech recognition, and sequence to sequence learning. However, this success has not been translated to applications like question answering that may involve complex arithmetic and logic reasoning. A major limitation of these models is in their inability to learn even simple arithmetic and logic operations. For example, it has been shown that neural networks fail to learn to add two binary numbers reliably. In this work, we propose Neural Programmer, an end-to-end differentiable neural network augmented with a small set of basic arithmetic and logic operations. Neural Programmer can call these augmented operations over several steps, thereby inducing compositional programs that are more complex than the built-in operations. The model learns from a weak supervision signal which is the result of execution of the correct program, hence it does not require expensive annotation of the correct program itself. The decisions of what operations to call, and what data segments to apply to are inferred by Neural Programmer. Such decisions, during training, are done in a differentiable fashion so that the entire network can be trained jointly by gradient descent. We find that training the model is difficult, but it can be greatly improved by adding random noise to the gradient. On a fairly complex synthetic table-comprehension dataset, traditional recurrent networks and attentional models perform poorly while Neural Programmer typically obtains nearly perfect accuracy."

>	"We develop Neural Programmer, a neural network model augmented with a small set of arithmetic and logic operations to perform complex arithmetic and logic reasoning. The model is fully differentiable and it can be trained in an end-to-end fashion to induce programs using much lesser sophisticated human supervision than prior work. It is a general model for program induction broadly applicable across different domains, data sources and languages. Our experiments indicate that the model is capable of learning with delayed supervision and exhibits powerful compositionality."

>	"While DNN models are capable of learning the fuzzy underlying patterns in the data, they have not had an impact in applications that involve crisp reasoning. A major limitation of these models is in their inability to learn even simple arithmetic and logic operations. For example, Joulin & Mikolov (2015) show that recurrent neural networks fail at the task of adding two binary numbers even when the result has less than 10 bits. This makes existing DNN models unsuitable for downstream applications that require complex reasoning, e.g., natural language question answering. For example, to answer the question “how many states border Texas?”, the algorithm has to perform an act of counting in a table which is something that a neural network is not yet good at. A fairly common method for solving these problems is program induction where the goal is to find a program (in SQL or some high-level languages) that can correctly solve the task. An application of these models is in semantic parsing where the task is to build a natural language interface to a structured database. This problem is often formulated as mapping a natural language question to an executable query. A drawback of existing methods in semantic parsing is that they are difficult to train and require a great deal of human supervision. As the space over programs is non-smooth, it is difficult to apply simple gradient descent; most often, gradient descent is augmented with a complex search procedure, such as sampling. To further simplify training, the algorithmic designers have to manually add more supervision signals to the models in the form of annotation of the complete program for every question or a domain-specific grammar. For example, designing grammars that contain rules to associate lexical items to the correct operations, e.g., the word “largest” to the operation “argmax”, or to produce syntactically valid programs, e.g., disallow the program >= dog. The role of hand-crafted grammars is crucial in semantic parsing yet also limits its general applicability to many different domains."

>	"The goal of this work is to develop a model that does not require substantial human supervision and is broadly applicable across different domains, data sources and natural languages. We propose Neural Programmer, an end-to-end differentiable neural network augmented with a small set of basic arithmetic and logic operations. In our formulation, the neural network can run several steps using a recurrent neural network. At each step, it can select a segment in the data source and a particular operation to apply to that segment. The neural network propagates these outputs forward at every step to form the final, more complicated output. Using the target output, we can adjust the network to select the right data segments and operations, thereby inducing the correct program. Key to our approach is that the selection process (for the data source and operations) is done in a differentiable fashion (i.e., soft selection or attention), so that the whole neural network can be trained jointly by gradient descent. At test time, we replace soft selection with hard selection. By combining neural network with mathematical operations, we can utilize both the fuzzy pattern matching capabilities of deep networks and the crisp algorithmic power of traditional programmable computers."

>	"Neural Programmer has two attractive properties. First, it learns from a weak supervision signal which is the result of execution of the correct program. It does not require the expensive annotation of the correct program for the training examples. The human supervision effort is in the form of question, data source and answer triples. Second, Neural Programmer does not require additional rules to guide the program search, making it a general framework. With Neural Programmer, the algorithmic designer only defines a list of basic operations which requires lesser human effort than in previous program induction techniques."

>	"We experiment with a synthetic table-comprehension dataset, consisting of questions with a wide range of difficulty levels. Examples of natural language translated queries include “print elements in column H whose field in column C is greater than 50 and field in column E is less than 20?” or “what is the difference between sum of elements in column A and number of rows in the table?”. We find that LSTM recurrent networks and LSTM models with attention do not work well. Neural Programmer, however, can completely solve this task or achieve greater than 99% accuracy on most cases by inducing the required latent program."

##
>	"Current neural networks cannot handle complex data structures."

>	"Current neural networks cannot handle numbers well: treat numbers as tokens, which lead to many unknown words."

>	"Current neural networks cannot make use of rules well: cannot use addition, subtraction, summation, average operations."

##
>	"Authors propose a neural programmer by defining a set of symbolic operations (e.g., argmax, greater than); at each step, all possible execution results are fused by a softmax layer, which predicts the probability of each operator at the current step. The step-by-step fusion is accomplished by weighted sum and the model is trained with mean square error. Hence, such approaches work with numeric tables, but may not be suited for other operations like string matching; it also suffers from the problem of “exponential numbers of combinatorial states.”"

  - http://youtu.be/KmOdBS4BXZ0?t=1h8m44s (Le)
  - http://distill.pub/2016/augmented-rnns/
  - https://github.com/tensorflow/models/tree/master/neural_programmer


#### Rocktaschel, Riedel - ["Learning Knowledge Base Inference with Neural Theorem Provers"](http://akbc.ws/2016/papers/14_Paper.pdf) (neural reasoning over knowledge base)
>	"In this paper we present a proof-of-concept implementation of Neural Theorem Provers, end-to-end differentiable counterparts of discrete theorem provers that perform first-order inference on vector representations of symbols using function-free, possibly parameterized, rules. As such, NTPs follow a long tradition of neural-symbolic approaches to automated knowledge base inference, but differ in that they are differentiable with respect to representations of symbols in a knowledge base and can thus learn representations of predicates, constants, as well as rules of predefined structure. Furthermore, they still allow us to incorporate domain knowledge provided as rules. The NTP presented here is realized via a differentiable version of the backward chaining algorithm. It operates on substitution representations and is able to learn complex logical dependencies from training facts of small knowledge bases."

>	"Our contributions are threefold: (i) we present the construction of an NTP based on differentiable backward chaining and unification, (ii) we show that when provided with rules this NTP can perform first-order inference in vector space like a discrete theorem prover would do on symbolic representations, and (iii) we demonstrate that NTPs can learn representations of symbols and first-order rules of predefined structure."

>	"We proposed neural theorem provers for knowledge base inference via differentiable backward chaining, which enables learning of symbol representations and parameters of rules of predefined structure. Our current implementation has severe computational limitations and does not scale to larger KBs as it investigates all possible proof paths. However, there are many possibilities to improve upon the presented architecture. For instance, one can batch-unify all rules whose right-hand side have the same structure and employ existing architectures such as Memory Networks or hierarchical attention for this task. Furthermore, it is possible to partition and batch rules not only by their right-hand side but also left-hand side structure to instantiate a single AND module for every partition. To further speed-up the prover, we want to investigate processing batches of queries, as well as differentiable ways of maintaining only the N best instead of all possible substitution representations at every depth of the prover. In addition, we will work on more flexible versions of neural theorem provers, for instance, where unification, rule selection and application itself are trainable functions, or where facts in a KB and goals can be natural language sentences."


#### Rocktaschel, Grefenstette, Hermann, Kocisky, Blunsom - ["Reasoning about Entailment with Neural Attention"](http://arxiv.org/abs/1509.06664) (neural reasoning over text)
>	"Automatically recognizing entailment relations between pairs of natural language sentences has so far been the dominion of classifiers employing hand engineered features derived from natural language processing pipelines. End-to-end differentiable neural architectures have failed to approach state-of-the-art performance until very recently. In this paper, we propose a neural model that reads two sentences to determine entailment using long short-term memory units. We extend this model with a word-by-word neural attention mechanism that encourages reasoning over entailments of pairs of words and phrases. Furthermore, we present a qualitative analysis of attention weights produced by this model, demonstrating such reasoning capabilities. On a large entailment dataset this model outperforms the previous best neural model and a classifier with engineered features by a substantial margin. It is the first generic end-to-end differentiable system that achieves state-of-the-art accuracy on a textual entailment dataset."

>	"In this paper, we show how the state-of-the-art in recognizing textual entailment on a large, human-curated and annotated corpus, can be improved with general end-to-end differentiable models. Our results demonstrate that LSTM recurrent neural networks that read pairs of sequences to produce a final representation from which a simple classifier predicts entailment, outperform both a neural baseline as well as a classifier with hand-engineered features. Furthermore, extending these models with attention over the premise provides further improvements to the predictive abilities of the system, resulting in a new state-of-the-art accuracy for recognizing entailment on the Stanford Natural Language Inference corpus. The models presented here are general sequence models, requiring no appeal to natural language specific processing beyond tokenization, and are therefore a suitable target for transfer learning through pre-training the recurrent systems on other corpora, and conversely, applying the models trained on this corpus to other entailment tasks. Future work will focus on such transfer learning tasks, as well as scaling the methods presented here to larger units of text (e.g. paragraphs and entire documents) using hierarchical attention mechanisms. Furthermore, we aim to investigate the application of these generic models to non-natural language sequential entailment problems."

  - http://egrefen.com/docs/HowMuchLinguistics2015.pdf
  - https://github.com/junfenglx/reasoning_attention


#### Li, Zemel, Brockschmidt, Tarlow - ["Gated Graph Sequence Neural Networks"](http://arxiv.org/abs/1511.05493) (neural reasoning over graphs)
>	"Graph-structured data appears frequently in domains including chemistry, natural language semantics, social networks, and knowledge bases. In this work, we study feature learning techniques for graph-structured inputs. Our starting point is previous work on Graph Neural Networks, which we modify to use gated recurrent units and modern optimization techniques and then extend to output sequences. The result is a flexible and broadly useful class of neural network models that has favorable inductive biases relative to purely sequence-based models (e.g., LSTMs) when the problem is graph-structured. We demonstrate the capabilities on some simple AI (bAbI) and graph algorithm learning tasks. We then show it achieves state-of-the-art performance on a problem from program verification, in which subgraphs need to be matched to abstract data structures."

>	"Many practical applications build on graph-structured data, and thus we often want to perform machine learning tasks that take graphs as inputs. Standard approaches to this problem include engineering custom features of an input graph, graph kernels, and methods that define graph features in terms of random walks on graphs. Our main contribution is an extension of Graph Neural Networks that outputs sequences. A secondary contribution is highlighting that Graph Neural Networks (and further extensions we develop here) are a broadly useful class of neural network model that is applicable to the problems currently facing the field. Previous work on feature learning for graph-structured inputs has focused on models that produce single outputs such as graph-level classifications, but many problems with graph inputs require outputting sequences. Examples include paths on a graph, enumerations of graph nodes with desirable properties, or sequences of global classifications mixed with, for example, a start and end node. We are not aware of existing graph feature learning work suitable for this problem. Our motivating application comes from program verification and requires outputting logical formulas, which we formulate as a sequential output problem."

>	"There are two settings for feature learning on graphs: (1) learning a representation of the input graph, and (2) learning representations of the internal state during the process of producing a sequence of outputs. Here, (1) is mostly achieved by previous work on Graph Neural Networks (Scarselli et al., 2009); we make several minor adaptations of this framework, including changing it to use modern practices around Recurrent Neural Networks. (2) is important because we desire outputs from graph-structured problems that are not solely individual classifications. In these cases, the challenge is how to learn features on the graph that encode the partial output sequence that has already been produced (e.g., the path so far if outputting a path) and that still needs to be produced (e.g., the remaining path). We will show how the GNN framework can be adapted to these settings, leading to a novel graph-based neural network model that we call Gated Graph Sequence Neural Networks."

>	"We discuss an application to the verification of computer programs. When attempting to prove properties such as memory safety (i.e., that there are no null pointer dereferences in a program), a core problem is to find mathematical descriptions of the data structures used in a program. Following Brockschmidt et al. (2015), we have phrased this as a machine learning problem where we will learn to map from a set of input graphs representing the state of memory to a logical description of the data structures that have been instantiated. Whereas Brockschmidt et al. (2015) relied on a large amount of hand-engineering of features, we show that the system can be replaced with a GGS-NN at no cost in accuracy."

>	"The results in the paper show that GGS-NNs have desirable inductive biases across a range of problems that have some intrinsic graph structure to them, and we believe there to be many more cases where GGS-NNs will be useful. There are, however, some limitations that need to be overcome to make them apply even more broadly. Two limitations that we mentioned previously are that the bAbI task translation does not incorporate temporal order of inputs or ternary and higher order relations. We can imagine several possibilities for lifting these restrictions, such as concatenating a series of GG-NNs, where there is one GG-NNs for each edge, and representing higher order relations as factor graphs. A more significant challenge is how to handle less structured input representations. For example, in the bAbI tasks it would be desirable not to use the symbolic form of the inputs. One possible approach is to incorporate less structured inputs, and latent vectors, in our GGS-NNs."

>	"The current GGS-NNs formulation specifies a question only after all the facts have been consumed. This implies that the network must try to derive all consequences of the seen facts and store all pertinent information to a node within its node representation. This is likely not ideal; it would be preferable to develop methods that take the question as an initial input, and then dynamically derive the facts needed to answer the question."

>	"We are particularly interested in continuing to develop end-to-end learnable systems that can learn about semantic properties of programs, that can learn more complicated graph algorithms, and in applying these ideas to problems that require reasoning over knowledge bases and databases. More generally, we consider these graph neural networks as representing a step towards a model that can combine structured representations with the powerful algorithms of deep learning, with the aim of taking advantage of known structure while learning and inferring how to reason with and extend these representations."

  - http://research.microsoft.com/apps/video/default.aspx?id=263975&r=1 (Li)


#### Zaremba, Kurach, Fergus - ["Learning to Discover Efficient Mathematical Identities"](http://arxiv.org/abs/1406.1584) (neural reasoning over formulas)
>	"In this paper we explore how machine learning techniques can be applied to the discovery of efficient mathematical identities. We introduce an attribute grammar framework for representing symbolic expressions. Given a grammar of math operators, we build trees that combine them in different ways, looking for compositions that are analytically equivalent to a target expression but of lower computational complexity. However, as the space of trees grows exponentially with the complexity of the target expression, brute force search is impractical for all but the simplest of expressions. Consequently, we introduce two novel learning approaches that are able to learn from simpler expressions to guide the tree search. The first of these is a simple n-gram model, the other being a recursive neural network. We show how these approaches enable us to derive complex identities, beyond reach of brute-force search, or human derivation."

  - http://youtube.com/watch?v=Hx20MUmWAfg (Fergus)
  - http://cs.nyu.edu/~zaremba/docs/Learning%20to%20manipulate%20symbols.pdf (Zaremba)


#### Beltagy, Roller, Cheng, Erk, Mooney - ["Representing Meaning with a Combination of Logical Form and Vectors"](http://arxiv.org/abs/1505.06816) (MLN reasoning over text and knowledge base)
>	"NLP tasks differ in the semantic information they require, and at this time no single semantic representation fulfills all requirements. Logic-based representations characterize sentence structure, but do not capture the graded aspect of meaning. Distributional models give graded similarity ratings for words and phrases, but do not adequately capture overall sentence structure. So it has been argued that the two are complementary. In this paper, we adopt a hybrid approach that combines logic-based and distributional semantics through probabilistic logic inference in Markov Logic Networks. We focus on textual entailment, a task that can utilize the strengths of both representations. Our system is three components, 1) parsing and task representation, where input RTE problems are represented in probabilistic logic. This is quite different from representing them in standard first-order logic. 2) knowledge base construction in the form of weighted inference rules from different sources like WordNet, paraphrase collections, and lexical and phrasal distributional rules generated on the fly. We use a variant of Robinson resolution to determine the necessary inference rules. More sources can easily be added by mapping them to logical rules; our system learns a resource-specific weight that counteract scaling differences between resources. 3) inference, where we show how to solve the inference problems efficiently. In this paper we focus on the SICK dataset, and we achieve a state-of-the-art result. Our system handles overall sentence structure and phenomena like negation in the logic, then uses our Robinson resolution variant to query distributional systems about words and short phrases. Therefore, we use our system to evaluate distributional lexical entailment approaches. We also publish the set of rules queried from the SICK dataset, which can be a good resource to evaluate them."

>	"Our approach has three main components:
>	1. Parsing and Task Representation, where input natural sentences are mapped into logic then used to represent the RTE task as a probabilistic inference problem.
>	2. Knowledge Base Construction, where the background knowledge is collected from different sources, encoded as first-order logic rules and weighted. This is where the distributional information is integrated into our system.
>	3. Inference, which solves the generated probabilistic logic problem using Markov Logic Networks."
>	"In the Inference step, automated reasoning for MLNs is used to perform the RTE task. We implement an MLN inference algorithm that directly supports querying complex logical formula, which is not supported in the available MLN tools. We exploit the closed-world assumption to help reduce the size of the inference problem in order to make it tractable."

>	"One powerful advantage of relying on a general-purpose probabilistic logic as a semantic representation is that it allows for a highly modular system. This means the most recent advancements in any of the system components, in parsing, in knowledge base resources and distributional semantics, and in inference algorithms, can be easily incorporated into the system."

>	"Being able to effectively represent natural languages semantics is important and has many important applications. We have introduced an approach that uses probabilistic logic to combine the expressivity and automated inference provided by logical representations, with the ability to capture graded aspects of natural language captured by distributional semantics. We evaluated this semantic representation on the RTE task which requires deep semantic understanding. Our system maps natural-language sentences to logical formulas, uses them to build probabilistic logic inference problems, builds a knowledge base from precompiled resources and on-the-fly distributional resources, then performs inference using Markov Logic. Experiments demonstrated state-of-the-art performance on the recently introduced SICK RTE task."

>	"Contextualization. The evaluation of the entailment rule classifier showed that some of the entailments are context-specific, like put/pour (which are entailing only for liquids) or push/knock (which is entailing in the context of “pushing a toddler into a puddle”). Cosine-based distributional features were able to identify some of these cases when all other features did not. We would like to explore whether contextualized distributional word representations, which take the sentence context into account, can identify such context-specific lexical entailments more reliably.
>	Distributional entailment. It is well-known that cosine similarity gives particularly high ratings to co-hyponyms, and our evaluation confirmed that this is a problem for lexical entailment judgments, as co-hyponyms are usually not entailing. However, co-hyponymy judgments can be used to position unknown terms in the WordNet hierarchy. This could be a new way of using distributional information in lexical entailment: using cosine similarity to position a term in an existing hierarchy, and then using the relations in the hierarchy for lexical entailment. While distributional similarity is usually used only on individual word pairs as if nothing else was known about the language, this technique would us distributional similarity to learn the meaning of unknown terms given that many other terms are already known.
>	Question Answering. Our semantic representation is a deep flexible semantic representation that can be used to perform various types of tasks. We are interested in applying our semantic representation to the question answering task. Question answering is the task of finding an answer of a WH question from large text corpus. This task is interesting because it may offer a wider variety of tasks to the distributional subsystem, including context-specific matches and the need to learn domain-specific distributional knowledge. In our framework, all the text would be translated to logic, and the question would be translated to a logical expression with an existentially quantified variable representing the questioned part. Then the probabilistic logic inference tool would aim to find the best entities in the text that fill in that existential quantifier in the question. Existing logic-based systems are usually applied to limited domains, such as querying a specific database, but with our system, we have the potential to query a large corpus because we are using Boxer for wide-coverage semantic analysis. The interesting bottleneck is the inference. It would be very challenging to scale probabilistic logic inference to such large inference problems.
>	Generalized Quantifiers. One important extension to this work is to support generalized quantifiers in probabilistic logic. Some determiners, such as “few” and “most”, cannot be represented in standard first-order logic, and are usually addressed using higher-order logics. But it could be possible to represent them using the probabilistic aspect of probabilistic logic, sidestepping the need for higher-order logic."
  - http://youtube.com/watch?v=OnlAQqkNpds (Beltagy)
  - http://youtube.com/watch?v=CmgGYn9KIpE (Erk)


#### Khot, Balasubramanian, Gribkoff, Sabharwal, Clark, Etzioni - ["Markov Logic Networks for Natural Language Question Answering"](http://arxiv.org/abs/1507.03045) (MLN reasoning over text)
>	"Our goal is to answer elementary-level science questions using knowledge extracted automatically from science textbooks, expressed in a subset of first-order logic. Given the incomplete and noisy nature of these automatically extracted rules, Markov Logic Networks seem a natural model to use, but the exact way of leveraging MLNs is by no means obvious. We investigate three ways of applying MLNs to our task. In the first, we simply use the extracted science rules directly as MLN clauses. Unlike typical MLN applications, our domain has long and complex rules, leading to an unmanageable number of groundings. We exploit the structure present in hard constraints to improve tractability, but the formulation remains ineffective. In the second approach, we instead interpret science rules as describing prototypical entities, thus mapping rules directly to grounded MLN assertions, whose constants are then clustered using existing entity resolution methods. This drastically simplifies the network, but still suffers from brittleness. Finally, our third approach, called Praline, uses MLNs to align the lexical elements as well as define and control how inference should be performed in this task. Our experiments, demonstrating a 15% accuracy boost and a 10x reduction in runtime, suggest that the flexibility and different inference semantics of Praline are a better fit for the natural language question answering task".
>	"Our investigation of the potential of MLNs for QA resulted in multiple formulations, the third of which is a flexible model that outperformed other, more natural approaches. We hope our question sets and MLNs will guide further research on improved modeling of the QA task and design of more efficient inference mechanisms for such models. While SRL methods seem a perfect fit for textual reasoning tasks such as RTE and QA, their performance on these tasks is still not up to par with simple textual feature-based approaches (Beltagy and Mooney 2014). On our datasets too, simple word-overlap based approaches perform quite well, scoring around 55%. We conjecture that the increased flexibility of complex relational models comes at the cost of increased susceptibility to noise in the input. Automatically learning weights of these models may allow leveraging this flexibility in order to handle noise better. Weight learning in these models, however, is challenging as we only observe the correct answer for a question and not intermediate feedback such as ideal alignments and desirable inference chains. Modeling the QA task with MLNs, an undirected model, gives the flexibility to define a joint model that allows alignment to influence inference and vice versa. At the same time, inference chains themselves need to be acyclic, suggesting that models such as Problog and SLP would be a better fit for this sub-task. Exploring hybrid formulation and designing more efficient and accurate MLNs or other SRL models for the QA task remains an exciting avenue of future research."

  - https://github.com/clulab/nlp-reading-group/raw/master/fall-2015-resources/Markov%20Logic%20Networks%20for%20Natural%20Language%20Question%20Answering.pdf
  - http://akbc.ws/2014/slides/etzioni-nips-akbc.pdf (slides 30-37)


#### Clark, Etzioni, Khot, Sabharwal, Tafjord, Turney - ["Combining Retrieval, Statistics, and Inference to Answer Elementary Science Questions"](http://web.engr.illinois.edu/~khashab2/files/2015_aristo/2015_aristo_aaai-2016.pdf)
>	"What capabilities are required for an AI system to pass standard 4th Grade Science Tests? Previous work has examined the use of Markov Logic Networks to represent the requisite background knowledge and interpret test questions, but did not improve upon an information retrieval baseline. In this paper, we describe an alternative approach that operates at three levels of representation and reasoning: information retrieval, corpus statistics, and simple inference over a semi-automatically constructed knowledge base, to achieve substantially improved results. We evaluate the methods on six years of unseen, unedited exam questions from the NY Regents Science Exam (using only non-diagram, multiple choice questions), and show that our overall system’s score is 71.3%, an improvement of 23.8% (absolute) over the MLN-based method described in previous work. We conclude with a detailed analysis, illustrating the complementary strengths of each method in the ensemble. Our datasets are being released to enable further research."

  - https://youtube.com/watch?v=HcPCURc59Vw (Sabharwal)


#### Khashabi, Khot, Sabharwal, Clark, Etzioni, Roth - ["Question Answering via Integer Programming over Semi-Structured Knowledge"](http://arxiv.org/abs/1604.06076)
>	"Answering science questions posed in natural language is an important AI challenge. Answering such questions often requires non-trivial inference and knowledge that goes beyond factoid retrieval. Yet, most systems for this task are based on relatively shallow Information Retrieval (IR) and statistical correlation techniques operating on large unstructured corpora. We propose a structured inference system for this task, formulated as an Integer Linear Program (ILP), that answers natural language questions using a semi-structured knowledge base derived from text, including questions requiring multi-step inference and a combination of multiple facts. On a dataset of real, unseen science questions, our system significantly outperforms (+14%) the best previous attempt at structured reasoning for this task, which used Markov Logic Networks (MLNs). It also improves upon a previous ILP formulation by 17.7%. When combined with unstructured inference methods, the ILP system significantly boosts overall performance (+10%). Finally, we show our approach is substantially more robust to a simple answer perturbation compared to statistical correlation methods."

>	"In contrast to a state-of-the-art structured inference method [Khot et al., 2015] for this task, which used Markov Logic Networks, TableILP achieves a significantly (+14% absolute) higher test score. This suggests that a combination of a rich and fine-grained constraint language, namely ILP, even with a publicly available solver is more effective in practice than various MLN formulations of the task. Further, while the scalability of the MLN formulations was limited to very few (typically one or two) selected science rules at a time, our approach easily scales to hundreds of relevant scientific facts. It also complements the kind of questions amenable to IR and PMI techniques, as is evidenced by the fact that a combination (trained using simple Logistic Regression of TableILP with IR and PMI results in a significant (+10% absolute) boost in the score compared to IR alone."

>	"Our ablation study suggests that combining facts from multiple tables or multiple rows within a table plays an important role in TableILP’s performance. We also show that TableILP benefits from the table structure, by comparing it with an IR system using the same knowledge (the table rows) but expressed as simple sentences; TableILP scores significantly (+10%) higher."

>	"Clark et al. [2016] proposed an ensemble approach for the science QA task, demonstrating the effectiveness of a combination of information retrieval, statistical association, rule-based reasoning, and an ILP solver operating on semi-structured knowledge. Our ILP system extends their model with additional constraints and preferences (e.g., semantic relation matching), substantially improving QA performance."

>	"The task of Recognizing Textual Entailment is also closely related, as QA can be cast as entailment (Does corpus entail question+answer?). However, RTE has primarily focused on the task of linguistic equivalence, and has not addressed questions where some form of scientific reasoning is required. Recent work on Natural Logic has extended RTE to account for the logical structure within language. Our work can be seen as going one step further, to add a layer of structured reasoning on top of this; in fact, we use an RTE engine as a basic subroutine for comparing individual table cells in our ILP formulation."

>	"We treat question answering as the task of pairing the question with an answer such that this pair has the best support in the knowledge base, measured in terms of the strength of a “support graph”. Informally, an edge denotes (soft) equality between a question or answer node and a table node, or between two table nodes. To account for lexical variability (e.g., that tool and instrument are essentially equivalent) and generalization (e.g., that a dog is an animal), we replace string equality with a phrase-level entailment or similarity function. A support graph thus connects the question constituents to a unique answer option through table cells and (optionally) table headers corresponding to the aligned cells. A given question and tables give rise to a large number of possible support graphs, and the role of the inference process will be to choose the “best” one under a notion of desirable support graphs developed next. We do this through a number of additional structural and semantic properties; the more properties the support graph satisfies, the more desirable it is."

  - https://youtube.com/watch?v=HcPCURc59Vw (Sabharwal)
  - https://github.com/allenai/tableilp


#### Li, Ritter, Jurafsky - ["Inferring User Preferences by Probabilistic Logical Reasoning over Social Networks"](http://arxiv.org/abs/1411.2679) (MLN reasoning over knowledge base)
>	"We propose a framework for inferring the latent attitudes or preferences of users by performing probabilistic first-order logical reasoning over the social network graph. Our method answers questions about Twitter users like "Does this user like sushi?" or "Is this user a New York Knicks fan?" by building a probabilistic model that reasons over user attributes (the user’s location or gender) and the social network (the user’s friends and spouse), via inferences like homophily (I am more likely to like sushi if spouse or friends like sushi, I am more likely to like the Knicks if I live in New York). The algorithm uses distant supervision, semi-supervised data harvesting and vector space models to extract user attributes (e.g. spouse, education, location) and preferences (likes and dislikes) from text. The extracted propositions are then fed into a probabilistic reasoner (we investigate both Markov Logic and Probabilistic Soft Logic). Our experiments show that probabilistic logical reasoning significantly improves the performance on attribute and relation extraction, and also achieves an F-score of 0.791 at predicting a users likes or dislikes, significantly better than two strong baselines."



---
### interesting papers - information extraction and integration

[selected papers](https://dropbox.com/sh/jmkl4mhajjghjxk/AABfAImA69Kzxx3b0IhCGouMa)  
[entity discovery and linking papers](http://nlp.cs.rpi.edu/kbp/2017/elreading.html)  


#### Wu, Hsiao, Cheng, Hancock, Rekatsinas, Levis, Re - ["Fonduer: Knowledge Base Construction from Richly Formatted Data"](http://arxiv.org/abs/1703.05028)
>	"We introduce Fonduer, a knowledge base construction framework for richly formatted information extraction, where entity relations and attributes are conveyed via structural, tabular, visual, and textual expressions. Fonduer introduces a new programming model for KBC built around a unified data representation that accounts for three challenging characteristics of richly formatted data: (1) prevalent document-level relations, (2) multimodality, and (3) data variety. Fonduer is the first KBC system for richly formatted data and uses a human-in-the-loop paradigm for training machine learning systems, referred to as data programming. Data programming softens the burden of traditional supervision by only asking users to provide lightweight functions that programmatically assign (potentially noisy) labels to the input data. Fonduer’s unified data model, together with data programming, allows users to use domain expertise as weak signals of supervision that help guide the KBC process over richly formatted data. We evaluate Fonduer on four real-world applications over different domains and achieve an average improvement of 42 F1 points over the upper bound of state-of-the-art approaches. In some domains, our users have produced up to 1.87× the number of correct entires compared to expert-curated public knowledge bases. Fonduer scales gracefully to millions of documents and is used in both academia and industry to create knowledge bases for real-world problems in many domains."

  - https://github.com/brylevkirill/notes/blob/test/Machine%20Learning.md#ratner-sa-wu-selsam-re---data-programming-creating-large-training-sets-quickly


#### Dong, Gabrilovich, Heitz, Horn, Murphy, Sun, Zhang - ["From Data Fusion to Knowledge Fusion"](http://www.vldb.org/pvldb/vol7/p881-dong.pdf) (information integration method used in Google Knowledge Vault)
>	"The task of data fusion is to identify the true values of data items (e.g., the true date of birth for Tom Cruise) among multiple observed values drawn from different sources (e.g., Web sites) of varying (and unknown) reliability. A recent survey has provided a detailed comparison of various fusion methods on Deep Web data. In this paper, we study the applicability and limitations of different fusion techniques on a more challenging problem: knowledge fusion. Knowledge fusion identifies true subject-predicate-object triples extracted by multiple information extractors from multiple information sources. These extractors perform the tasks of entity linkage and schema alignment, thus introducing an additional source of noise that is quite different from that traditionally considered in the data fusion literature, which only focuses on factual errors in the original sources. We adapt state-of-the-art data fusion techniques and apply them to a knowledge base with 1.6B unique knowledge triples extracted by 12 extractors from over 1B Web pages, which is three orders of magnitude larger than the data sets used in previous data fusion papers. We show great promise of the data fusion approaches in solving the knowledge fusion problem, and suggest interesting research directions through a detailed error analysis of the methods."

  - http://lunadong.com/talks/fromDFtoKF.pdf


#### West, Gabrilovich, Murphy, Sun, Gupta, Lin - ["Knowledge Base Completion via Search-Based Question Answering"](http://www.cs.ubc.ca/~murphyk/Papers/www14.pdf) (knowledge base completion method used in Google Knowledge Vault)
>	"Over the past few years, massive amounts of world knowledge have been accumulated in publicly available knowledge bases, such as Freebase, NELL, and YAGO. Yet despite their seemingly huge size,
these knowledge bases are greatly incomplete. For example, over 70% of people included in Freebase have no known place of birth, and 99% have no known ethnicity. In this paper, we propose a way to leverage existing Web-search–based question-answering technology to fill in the gaps in knowledge bases in a targeted way. In particular, for each entity attribute, we learn the best set of queries to ask, such that the answer snippets returned by the search engine are most likely to contain the correct value for that attribute. For example, if we want to find Frank Zappa’s mother, we could ask the query who is the mother of Frank Zappa. However, this is likely to return ‘The Mothers of Invention’, which was the name of his band. Our system learns that it should (in this case) add disambiguating terms, such as Zappa’s place of birth, in order to make it more likely that the search results contain snippets mentioning his mother. Our system also learns how many different queries to ask for each attribute, since in some cases, asking too many can hurt accuracy (by introducing false positives). We discuss how to aggregate candidate answers across multiple queries, ultimately returning probabilistic predictions for possible values for each attribute. Finally, we evaluate our system and show that it is able to extract a large number of facts with high confidence."


#### Gupta, Halevy, Wang, Whang, Wu - ["Biperpedia: An Ontology for Search Applications"](http://www.vldb.org/pvldb/vol7/p505-gupta.pdf) (automated ontology construction method used in Google Knowledge Vault)
>	"Search engines make significant efforts to recognize queries that can be answered by structured data and invest heavily in creating and maintaining high-precision databases. While these databases have a relatively wide coverage of entities, the number of attributes they model (e.g., GDP, CAPITAL, ANTHEM) is relatively small. Extending the number of attributes known to the search engine can enable it to more precisely answer queries from the long and heavy tail, extract a broader range of facts from the Web, and recover the semantics of tables on the Web. We describe Biperpedia, an ontology with 1.6M (class, attribute) pairs and 67K distinct attribute names. Biperpedia extracts attributes from the query stream, and then uses the best extractions to seed attribute extraction from text. For every attribute Biperpedia saves a set of synonyms and text patterns in which it appears, thereby enabling it to recognize the attribute in more contexts. In addition to a detailed analysis of the quality of Biperpedia, we show that it can increase the number of Web tables whose semantics we can recover by more than a factor of 4 compared with Freebase."


#### Ji, Nothman, Hachey - ["Overview of TAC-KBP2014 Entity Discovery and Linking Tasks"](http://nlp.cs.rpi.edu/paper/edl2014overview.pdf)
>	"In this paper we give an overview of the Entity Discovery and Linking tasks at the Knowledge Base Population track at TAC 2014. In this year we introduced a new end-to-end English entity discovery and linking task which requires a system to take raw texts as input, automatically extract entity mentions, link them to a knowledge base, and cluster NIL mentions. In this paper we provide an overview of the task definition, annotation issues, successful methods and research challenges associated with this new task. This new task has attracted a lot of participants and has intrigued many interesting research problems and potential approaches."


#### Surdeanu, Ji - ["Overview of the English Slot Filling Task at the TAC2014 Knowledge Base Population Evaluation"](http://nlp.cs.rpi.edu/paper/sf2014overview.pdf)
>	"We overview the English Slot Filling track of the TAC2014 Knowledge Base Population evaluation. The goal of this KBP track is to promote research in the extraction of binary relations between named and numeric entities from free text. The main changes this year include: (a) the inclusion of ambiguous queries, i.e., queries that point to multiple real-life entities with the same name; (b) accepting outputs created through inference; and (c) a simplification of the task and of the input format by removing references to the knowledge base for the entities included in queries."

>	"It is important to note that SF systems are still far from human performance on this task. The top system this year achieves 52% of human performance, and the median system is at only 28% of human performance. We are still far from solving the SF problem."


#### Angeli, Gupta, Jose, Manning, Re, Tibshirani, Wu, Zhang - ["Stanford’s 2014 Slot Filling Systems"](http://i.stanford.edu/hazy/papers/2014kbp-systemdescription.pdf) (DeepDive, winner of TAC-KBP 2014 English Slot Filling challenge)
>	"We describe Stanford’s entry in the TACKBP 2014 Slot Filling challenge. We submitted two broad approaches to Slot Filling: one based on the DeepDive framework (Niu et al., 2012), and another based on the multi-instance multi-label relation extractor of Surdeanu et al. (2012). In addition, we evaluate the impact of learned and hard-coded patterns on performance for slot filling, and the impact of the partial annotations described in Angeli et al. (2014)."

>	"We describe Stanford’s two systems in the 2014 KBP Slot Filling competition. The first, and best performing system, is built on top of the DeepDive framework. The central lesson we would like to emphasize from this system is that leveraging large computers allows for completely removing the information retrieval component of a traditional KBP system, and allows for quick turnaround times while processing the entire source corpus as a single unit. DeepDive offers a convenient framework for developing systems on these large computers, including defining the pre-processing pipelines (feature engineering, entity linking, mention detection, etc.) and then defining and training a relation extraction model. The second system Stanford submitted is based around the MIML-RE relation extractor, following closely from the 2013 submission, but with the addition of learned patterns, and with MIML-RE trained fixing carefully selected manually annotated sentences. The central lesson we would like to emphasize from this system is that a relatively small annotation effort (10k sentences) over carefully selected examples can yield a surprisingly large gain in end-to-end performance on the Slot Filling task."

>	"In DeepDive, calibration plots are used to summarize the overall quality of the results. Because DeepDive uses a joint probability model, each random variable is assigned a marginal probability. Ideally, if one takes all the facts to which DeepDive assigns a probability score of 0.95, then 95% of these facts are correct. We believe that probabilities remove a key element: the developer reasons about features, not the algorithms underneath. This is a type of algorithm independence that we believe is critical."


#### Suchanek, Abiteboul, Senellart - ["PARIS: Probabilistic Alignment of Relations, Instances, and Schema"](https://www.lri.fr/~cr/Publications_Master_2013/Brigitte_Safar/p157_fabianmsuchanek_vldb2011.pdf)
>	"One of the main challenges that the Semantic Web faces is the integration of a growing number of independently designed ontologies. In this work, we present paris, an approach for the automatic alignment of ontologies. PARIS aligns not only instances, but also relations and classes. Alignments at the instance level cross-fertilize with alignments at the schema level. Thereby, our system provides a truly holistic solution to the problem of ontology alignment. The heart of the approach is probabilistic, i.e., we measure degrees of matchings based on probability estimates. This allows PARIS to run without any parameter tuning. We demonstrate the efficiency of the algorithm and its precision through extensive experiments. In particular, we obtain a precision of around 90% in experiments with some of the world’s largest ontologies."

>	"We have presented PARIS, an algorithm for the automated alignment of RDFS ontologies. Unlike most other approaches, PARIS computes alignments not only for instances, but also for classes and relations. It does not need training data and it does not require any parameter tuning. PARIS is based on a probabilistic framework that captures the interplay between schema alignment and instance matching in a natural way, thus providing a holistic solution to the ontology alignment problem. Experiments show that our approach works extremely well in practice. PARIS does not use any kind of heuristics on relation names, which allows aligning relations with completely different names. We conjecture that the name heuristics of more traditional schema-alignment techniques could be factored into the model. Currently, PARIS cannot deal with structural heterogeneity. If one ontology models an event by a relation (such as wonAward), while the other one models it by an event entity (such as winningEvent, with relations winner, award, year), then paris will not be able to find matches. The same applies if one ontology is more fine-grained than the other one (specifying, e.g., cities as birth places instead of countries), or if one ontology treats cities as entities, while the other one refers to them by strings."


#### Wijaya, Talukdar, Mitchell - ["PIDGIN: Ontology Alignment using Web Text as Interlingua"](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.412.6159)
>	"The problem of aligning ontologies and database schemas across different knowledge bases and databases is fundamental to knowledge management problems, including the problem of integrating the disparate knowledge sources that form the semantic web’s Linked Data. We present a novel approach to this ontology alignment problem that employs a very large natural language text corpus as an interlingua to relate different knowledge bases. The result is a scalable and robust method that aligns relations and categories across different KBs by analyzing both (1) shared relation instances across these KBs, and (2) the verb phrases in the text instantiations of these relation instances. Experiments with PIDGIN demonstrate its superior performance when aligning ontologies across large existing KBs including NELL, Yago and Freebase. Furthermore, we show that in addition to aligning ontologies, PIDGIN can automatically learn from text, the verb phrases to identify relations, and can also type the arguments of relations of different KBs."

>	"In this paper we introduce PIDGIN, a novel, flexible, and scalable approach to automatic alignment of real-world KB ontologies, demonstrating its superior performance at aligning large real-world KB ontologies including those of NELL, Yago and Freebase. The key idea in PIDGIN is to align KB ontologies by integrating two types of information: relation instances that are shared by the two KBs, and mentions of the KB relation instances across a large text corpus. PIDGIN uses a natural language web text corpus of 500 million dependency-parsed documents as interlingua and a graph-based self-supervised learning to infer alignments. To the best of our knowledge, this is the first successful demonstration of using such a large text resource for ontology alignment. PIDGIN is self-supervised, and does not require human labeled data. Moreover, PIDGIN can be implemented in MapReduce, making it suitable for aligning ontologies from large KBs. We have provided extensive experimental results on multiple real world datasets, demonstrating that PIDGIN significantly outperforms PARIS, the current state-of-the-art approach to ontology alignment. We observe in particular that PIDGIN is typically able to improve recall over that of PARIS, without degradation in precision. This is presumably due to PIDGIN’s ability to use text-based interlingua to establish alignments when there are few or no relation instances shared by the two KBs. Additionally, PIDGIN automatically learns which verbs are associated with which ontology relations. These verbs can be used in the future to extract new instances to populate the KB or identify relations between entities in documents. PIDGIN can also assign relations in one KB with argument types of another KB. This can help type relations that do not yet have argument types, like that of KBP. Argument typing can improve the accuracy of extraction of new relation instances by constraining the instances to have the correct types. In the future, we plan to extend PIDGIN’s capabilities to provide explanations for its inferred alignments. We also plan to experiment with aligning ontologies from more than two KBs simultaneously."

  - https://github.com/kushalarora/pidgin


#### Hu, Ma, Liu, Hovy, Xing - ["Harnessing Deep Neural Networks with Logic Rules"](http://arxiv.org/abs/1603.06318) (named entity recognition)
>	"Combining deep neural networks with structured logic rules is desirable to harness flexibility and reduce unpredictability of the neural models. We propose a general framework capable of enhancing various types of neural networks (e.g., CNNs and RNNs) with declarative first-order logic rules. Specifically, we develop an iterative distillation method that transfers the structured information of logic rules into the weights of neural networks. We deploy the framework on a CNN for sentiment analysis, and an RNN for named entity recognition. With a few highly intuitive rules, we obtain substantial improvements and achieve state-of-the-art or comparable results to previous best-performing systems."

>	"We have developed a framework which combines deep neural networks with first-order logic rules to allow integrating human knowledge and intentions into the neural models. In particular, we proposed an iterative distillation procedure that transfers the structured information of logic rules into the weights of neural networks. The transferring is done via a teacher network constructed using the posterior regularization principle. Our framework is general and applicable to various types of neural architectures. With a few intuitive rules, our framework significantly improves base networks on sentiment analysis and named entity recognition, demonstrating the practical significance of our approach. The encouraging results indicate a strong potential of our approach on improving other NLP tasks and application domains. We plan to explore more applications and incorporate more structured knowledge in neural networks. We also would like to improve our framework to automatically learn the importance of different rules, and derive new rules from data."

>	"Despite the impressive advances, the widely-used DNN methods still have limitations. The high predictive accuracy has heavily relied on large amounts of labeled data; and the purely data-driven learning can lead to uninterpretable and sometimes counter-intuitive results. It is also difficult to encode human intention to guide the models to capture desired patterns, without expensive direct supervision or ad-hoc initialization. On the other hand, the cognitive process of human beings have indicated that people learn not only from concrete examples (as DNNs do) but also from different forms of general knowledge and rich experiences. Logic rules provide a flexible declarative language for communicating high-level cognition and expressing structured knowledge. It is therefore desirable to integrate logic rules into DNNs, to transfer human intention and domain knowledge to neural models, and regulate the learning process."

>	"We present a framework capable of enhancing general types of neural networks, such as convolutional networks and recurrent networks, on various tasks, with logic rule knowledge. Our framework enables a neural network to learn simultaneously from labeled instances as well as logic rules, through an iterative rule knowledge distillation procedure that transfers the structured information encoded in the logic rules into the network parameters. Since the general logic rules are complementary to the specific data labels, a natural “side-product” of the integration is the support for semi-supervised learning where unlabeled data can be used to better absorb the logical knowledge. Methodologically, our approach can be seen as a combination of the knowledge distillation and the posterior regularization method. In particular, at each iteration we adapt the posterior constraint principle from PR to construct a rule-regularized teacher, and train the student network of interest to imitate the predictions of the teacher network. We leverage soft logic to support flexible rule encoding."

>	"We apply the proposed framework on both CNN and RNN, and deploy on the task of sentiment analysis and named entity recognition, respectively. With only a few (one or two) very intuitive rules, the enhanced networks strongly improve over their basic forms (without rules), and achieve better or comparable performance to state-of-the-art models which typically have more parameters and complicated architectures. By incorporating the bi-gram transition rules, we obtain 1.56 improvement in F1 score that outperforms all previous neural based methods on named entity recognition task, including the BLSTM-CRF model which applies a conditional random field on top of a BLSTM model in order to capture the transition patterns and encourage valid sequences. In contrast, our method implements the desired constraints in a more straightforward way by using the declarative logic rule language, and at the same time does not introduce extra model parameters to learn. Further integration of the list rule provides a second boost in performance, achieving an F1 score very close to the best-performing system Joint-NER-EL which is a probabilistic graphical model based method optimizing NER and entity linking jointly and using large amount of external resources."

  - http://www.erogol.com/harnessing-deep-neural-networks-with-logic-rules/


#### Durrett, Klein - ["A Joint Model for Entity Analysis: Coreference, Typing, and Linking"](http://www.eecs.berkeley.edu/~gdurrett/papers/durrett-klein-tacl2014.pdf)
>	"We present a joint model of three core tasks in the entity analysis stack: coreference resolution (within-document clustering), named entity recognition (coarse semantic typing), and entity linking (matching to Wikipedia entities). Our model is formally a structured conditional random field. Unary factors encode local features from strong baselines for each task. We then add binary and ternary factors to capture cross-task interactions, such as the constraint that coreferent mentions have the same semantic type. On the ACE 2005 and OntoNotes datasets, we achieve state-of-the-art results for all three tasks. Moreover, joint modeling improves performance on each task over strong independent baselines."

  - http://nlp.cs.berkeley.edu/projects/entity.shtml
  - http://techtalks.tv/talks/a-joint-model-for-entity-analysis-coreference-typing-and-linking/61534/


#### Wiseman, Rush, Shieber, Weston - ["Learning Anaphoricity and Antecedent Ranking Features for Coreference Resolution"](http://people.seas.harvard.edu/~srush/acl15.pdf)
>	"We introduce a simple, non-linear mention-ranking model for coreference resolution that attempts to learn distinct feature representations for anaphoricity detection and antecedent ranking, which we encourage by pre-training on a pair of corresponding subtasks. Although we use only simple, unconjoined features, the model is able to learn useful representations, and we report the best overall score on the CoNLL 2012 English test set to date."

>	"In this work, we propose a data-driven model for coreference that does not require prespecifying any feature relationships. Inspired by recent work in learning representations for natural language tasks (Collobert et al., 2011), we explore neural network models which take only raw, unconjoined features as input, and attempt to learn intermediate representations automatically. In particular, the model we describe attempts to create independent feature representations useful for both detecting the anaphoricity of a mention (that is, whether or not a mention is anaphoric) and ranking the potential antecedents of an anaphoric mention. Adequately capturing anaphoricity information has long been thought to be an important aspect of the coreference task, since a strong non-anaphoric signal might, for instance, discourage the erroneous prediction of an antecedent for a non-anaphoric mention even in the presence of a misleading head match. We furthermore attempt to encourage the learning of the desired feature representations by pretraining the model’s weights on two corresponding subtasks, namely, anaphoricity detection and antecedent ranking of known anaphoric mentions."

>	"We have presented a simple, local model capable of learning feature representations useful for coreference-related subtasks, and of thereby achieving state-of-the-art performance. Because our approach automatically learns intermediate representations given raw features, directions for further research might alternately explore including additional (perhaps semantic) raw features, as well as developing loss functions that further discourage learning representations that allow for common errors (such as those involving pleonastic pronouns)."

  - https://github.com/swiseman/nn_coref


#### Mintz, Bills, Snow, Jurafsky - ["Distant Supervision for Relation Extraction without Labeled Data"](http://web.stanford.edu/~jurafsky/mintz.pdf)
>	"Modern models of relation extraction for tasks like ACE are based on supervised learning of relations from small hand-labeled corpora. We investigate an alternative paradigm that does not require labeled corpora, avoiding the domain dependence of ACE style algorithms, and allowing the use of corpora of any size. Our experiments use Freebase, a large semantic database of several thousand relations, to provide distant supervision. For each pair of entities that appears in some Freebase relation, we find all sentences containing those entities in a large unlabeled corpus and extract textual features to train a relation classifier. Our algorithm combines the advantages of supervised IE (combining 400,000 noisy pattern features in a probabilistic classifier) and unsupervised IE (extracting large numbers of relations from large corpora of any domain). Our model is able to extract 10,000 instances of 102 relations at a precision of 67.6%. We also analyze feature performance, showing that syntactic parse features are particularly helpful for relations that are ambiguous or lexically distant in their expression."


#### Xu, Hoffman, Zhao, Grishman - ["Filling Knowledge Base Gaps for Distant Supervision of Relation Extraction"](https://aclweb.org/anthology/P/P13/P13-2117.pdf)
>	"Distant supervision has attracted recent interest for training information extraction systems because it does not require any human annotation but rather employs existing knowledge bases to heuristically label a training corpus. However, previous work has failed to address the problem of false negative training examples mislabeled due to the incompleteness of knowledge bases. To tackle this problem, we propose a simple yet novel framework that combines a passage retrieval model using coarse features into a state-of-the-art relation extractor using multi-instance learning with fine features. We adapt the information retrieval technique of pseudo-relevance feedback to expand knowledge bases, assuming entity pairs in top-ranked passages are more likely to express a relation. Our proposed technique significantly improves the quality of distantly supervised relation extraction, boosting recall from 47.7% to 61.2% with a consistently high level of precision of around 93% in the experiments."


#### Weston, Bordes, Yakhnenko, Usunier - ["Connecting Language and Knowledge Bases with Embedding Models for Relation Extraction"](http://arxiv.org/abs/1307.7973)
>	"This paper proposes a novel approach for relation extraction from free text which is trained to jointly use information from the text and from existing knowledge. Our model is based on two scoring functions that operate by learning low-dimensional embeddings of words and of entities and relationships from a knowledge base. We empirically show on New York Times articles aligned with Freebase relations that our approach is able to efficiently use the extra information provided by a large subset of Freebase data (4M entities, 23k relationships) to improve over existing methods that rely on text features alone."

  - http://youtu.be/YkVvOBylV5k?t=9m47s


#### Faruqui, Kumar - ["Multilingual Open Relation Extraction Using Cross-lingual Projection"](http://arxiv.org/abs/1503.06450)
>	"Open domain relation extraction systems identify relation and argument phrases in a sentence without relying on any underlying schema. However, current state-of-the-art relation extraction systems are available only for English because of their heavy reliance on linguistic tools such as part-of-speech taggers and dependency parsers. We present a cross-lingual annotation projection method for language independent relation extraction. We evaluate our method on a manually annotated test set and present results on three typologically different languages. We release these manual annotations and extracted relations in 61 languages from Wikipedia."

>	"We utilized OLLIE to extract the relation tuples for every English sentence. We chose OLLIE because it has been shown to give a higher yield at comparable precision relative to other open RE systems such as REVERB and WOEparse. OLLIE was trained by extracting dependency path patterns on annotated training data. This training data was bootstrapped from a set of high precision seed tuples extracted from a simpler RE system REVERB."

  - http://googleresearch.blogspot.ru/2015/06/a-multilingual-corpus-of-automatically.html


#### Santos, Xiang, Zhou - ["Classifying Relations by Ranking with Convolutional Neural Networks"](http://arxiv.org/abs/1504.06580)
>	"Relation classification is an important semantic processing task for which state-of-the-art systems still rely on costly handcrafted features. In this work we tackle the relation classification task using a convolutional neural network that performs classification by ranking. We propose a new pairwise ranking loss function that makes it easy to reduce the impact of artificial classes. We perform experiments using the the SemEval-2010 Task 8 dataset, which is designed for the task of classifying the relationship between two nominals marked in a sentence. Using CR-CNN, we outperform the state-of-the-art for this dataset and achieve a F1 of 84.1 without using any costly handcrafted features. Additionally, our experimental results show that: (1) our approach is more effective than CNN followed by a softmax classifier; (2) omitting the representation of the artificial class Other improves both precision and recall; and (3) using only word embeddings as input features is enough to achieve state-of-the-art results if we consider only the text between the two target nominals."


#### Xu, Feng, Huang, Zhao - ["Semantic Relation Classification via Convolutional Neural Networks with Simple Negative Sampling"](http://arxiv.org/abs/1506.07650)
>	"Syntactic features play an essential role in identifying relationship in a sentence. Previous neural network models often suffer from irrelevant information introduced when subjects and objects are in a long distance. In this paper, we propose to learn more robust relation representations from the shortest dependency path through a convolution neural network. We further propose a straightforward negative sampling strategy to improve the assignment of subjects and objects. Experimental results show that our method outperforms the state-of-the-art methods on the SemEval-2010 Task 8 dataset."

>	"In this paper, we exploit a convolution neural network to learn more robust and effective relation representations from shortest dependency paths for relation extraction. We further propose a simple negative sampling method to help make correct assignments for subjects and objects within a relationship. Experimental results show that our model significantly outperforms state-of-the-art systems and our treatment to dependency paths can well capture the syntactic features for relation extraction."

  - https://youtube.com/watch?v=bwAGtKqkNGU (Xu)


#### Miwa, Bansal - ["End-to-end Relation Extraction using LSTMs on Sequences and Tree Structures"](http://arxiv.org/abs/1601.00770)
>	"We present a novel end-to-end neural model to extract entities and relations between them. Our recurrent neural network based model stacks bidirectional sequential LSTM-RNNs and bidirectional tree-structured LSTM-RNNs to capture both word sequence and dependency tree substructure information. This allows our model to jointly represent both entities and relations with shared parameters. We further encourage detection of entities during training and use of entity information in relation extraction via curriculum learning and scheduled sampling. Our model improves over the state-of-the-art feature-based model on end-to-end relation extraction, achieving 3.5% and 4.8% relative error reductions in F-score on ACE2004 and ACE2005, respectively. We also show improvements over the state-of-the-art convolutional neural network based model on nominal relation classification (SemEval-2010 Task 8), with 2.5% relative error reduction in F-score."


#### Galarraga, Heitz, Murphy, Suchanek - ["Canonicalizing Open Knowledge Bases"](http://suchanek.name/work/publications/cikm2014.pdf)
>	"Open information extraction approaches have led to the creation of large knowledge bases from the Web. The problem with such methods is that their entities and relations are not canonicalized, leading to redundant and ambiguous facts. For example, they may store <Barack Obama, was born in, Honolulu> and <Obama, place of birth, Honolulu>. In this paper, we present an approach based on machine learning methods that can canonicalize such Open IE triples, by clustering synonymous names and phrases. We also provide a detailed discussion about the different signals, features and design choices that influence the quality of synonym resolution for noun phrases in Open IE KBs, thus shedding light on the middle ground between “open” and “closed” information extraction systems."

>	"We have shown that it is possible, using fairly simple and standard machine learning techniques, to identify synonym mentions in a reasonable fraction of the triples coming from standard Open IE systems, such as Reverb and NELL. Our results suggest that, even with a certain level of ambiguity, the IDF token overlap is the strongest signal of synonymy for noun phrases on the Web, whereas more sophisticated features extracted from the sources are insufficient for this task on their own. We also provided useful and novel insights about the impact of canopies in the performance of Hierarchical Agglomerative Clustering, a standard technique for record linkage and identification of synonyms. The resulting clusters of entities and relations are semantically meaningful; some of them correspond to existing entities and predicates in Freebase, but others are novel extensions. We believe this hybrid approach - whereby we use high recall extractors, followed by clustering methods to improve the precision - shows great promise for bridging the gap between Open and Closed IE methods for knowledge base construction."


#### Li, Dong, Lyons, Meng, Srivastava - ["Truth Finding on the Deep Web: Is the Problem Solved?"](http://www.vldb.org/pvldb/vol6/p97-li.pdf)
>	"The amount of useful information available on the Web has been growing at a dramatic pace in recent years and people rely more and more on the Web to fulfill their information needs. In this paper, we study truthfulness of Deep Web data in two domains where we believed data are fairly clean and data quality is important to people’s lives: Stock and Flight. To our surprise, we observed a large amount of inconsistency on data from different sources and also some sources with quite low accuracy. We further applied on these two data sets state-of-the-art data fusion methods that aim at resolving conflicts and finding the truth, analyzed their strengths and limitations, and suggested promising research directions. We wish our study can increase awareness of the seriousness of conflicting data on the Web and in turn inspire more research in our community to tackle this problem."


#### Dong, Berti-Equille, Srivastava - ["Data Fusion: Resolving Conflicts from Multiple Sources"](http://static.googleusercontent.com/media/research.google.com/en//pubs/archive/41657.pdf)
>	"Many data management applications, such as setting up Web portals, managing enterprise data, managing community data, and sharing scientific data, require integrating data from multiple sources. Each of these sources provides a set of values and different sources can often provide conflicting values. To present quality data to users, it is critical to resolve conflicts and discover values that reflect the real world; this task is called data fusion. This paper describes a novel approach that finds true values from conflicting information when there are a large number of sources, among which some may copy from others. We present a case study on real-world data showing that the described algorithm can significantly improve accuracy of truth discovery and is scalable when there are a large number of data sources."


#### Dong, Gabrilovich, Murphy, Dang, Horn, Lugaresi, Sun, Zhang - ["Knowledge-Based Trust: Estimating the Trustworthiness of Web Sources"](http://arxiv.org/abs/1502.03519) (Google Knowledge Vault)
>	"The quality of web sources has been traditionally evaluated using exogenous signals such as the hyperlink structure of the graph. We propose a new approach that relies on endogenous signals, namely, the correctness of factual information provided by the source. A source that has few false facts is considered to be trustworthy. The facts are automatically extracted from each source by information extraction methods commonly used to construct knowledge bases. We propose a way to distinguish errors made in the extraction process from factual errors in the web source per se, by using joint inference in a novel multi-layer probabilistic model. We call the trustworthiness score we computed Knowledge-Based Trust. On synthetic data, we show that our method can reliably compute the true trustworthiness levels of the sources. We then apply it to a database of 2.8B facts extracted from the web, and thereby estimate the trustworthiness of 119M webpages. Manual evaluation of a subset of the results confirms the effectiveness of the method."

>	"challenges:
>	 - how to detect if triple is indeed claimed by the source instead of an extraction error?
>	 - how to compute well-calibrated triple probability?
>	 - how to handle too large sources or too small sources?"
>	"strategies:
>	1. Graphical model - predict at the same time:
>	 - extraction correctness
>	 - triple correctness
>	 - source accuracy
>	 - extractor precision/recall
>	2. un(semi-)supervised learning (Bayesian)
>	 - leverage source/extractor agreements
>	 - trust a source/extractor with high quality
>	3. source/extractor hierarchy
>	 - break down "large" sources
>	 - group "small" sources"
>	"Fact is more likely to be correct if extracted by high-precision sources; more likely to be wrong if not extracted by high-recall sources."

>	"algorithm:
>	 - compute P(web source provides triple | extractor quality) by Bayesian analysis (E-step)
>	 - compute P(T | web source quality) by Bayesian analysis (E-step)
>	 - compute source accuracy (M-step)
>	 - compute extractor precision and recall (M-step)"
>	"This paper proposes a new metric for evaluating web-source quality - knowledge-based trust. We proposed a sophisticated probabilistic model that jointly estimates the correctness of extractions and source data, and the trustworthiness of sources. In addition, we presented an algorithm that dynamically decides the level of granularity for each source. Experimental results have shown both promise in evaluating web source quality and improvement over existing techniques for knowledge fusion."

  - "Knowledge Vault and Knowledge-Based Trust" - http://youtube.com/watch?v=Z6tmDdrBnpU (Dong)


#### Nakashole, Mitchell - ["Language-Aware Truth Assessment of Fact Candidates"](https://aclweb.org/anthology/P/P14/P14-1095.pdf)
>	"This paper introduces FactChecker, language-aware approach to truth-finding. FactChecker differs from prior approaches in that it does not rely on iterative peer voting, instead it leverages language to infer believability of fact candidates. In particular, FactChecker makes use of linguistic features to detect if a given source objectively states facts or is speculative and opinionated. To ensure that fact candidates mentioned in similar sources have similar believability, FactChecker augments objectivity with a co-mention score to compute the overall believability score of a fact candidate. Our experiments on various datasets show that FactChecker yields higher accuracy than existing approaches."

>	"Prior truth-finding methods are mostly based on iterative voting, where votes are propagated from sources to fact candidates and then back to sources. At the core of iterative voting is the assumption that candidates mentioned by many sources are more likely to be true. However, additional aspects of a source influence its trustworthiness, besides external votes. Our goal is to accurately assess truthfulness of fact candidates by taking into account the language of sources that mention them. A Mechanical Turk study we carried out revealed that there is a significant correlation between objectivity of language and trustworthiness of sources. Objectivity of language refers to the use of neutral, impartial language, which is not personal, judgmental, or emotional. Trustworthiness refers to a source of information being reliable and truthful. We use linguistics features to detect if a given source objectively states facts or is speculative and opinionated. Additionally, in order to ensure that fact candidates mentioned in similar sources have similar believability scores, our believability computation model incorporates influence of comentions. However, we must avoid falsely boosting co-mentioned fact candidates. Our model addresses potential false boosts in two ways: first, by ensuring that co-mention influence is only propagated to related fact candidates; second, by ensuring that the degree of co-mention influence is determined by the trustworthiness of the sources in which co-mentions occur."

>	"More precisely, we make the following contributions: (1) Alternative Fact Candidates: Truth-finders rank a given fact candidate with respect to its alternatives. For example, alternative places where Barack Obama could have been born. Virtually all existing truth-finders assume that the alternatives are provided. In contrast, we developed a method for generating alternative fact candidates. (2) Objectivity-Trustworthiness Correlation: We hypothesize that objectivity of language and trustworthiness of sources are positively correlated. To test this hypothesis, we designed a Mechanical Turk study. The study showed that this correlation does in fact hold. (3) Objectivity Classifier: Using labeled data from the Mechanical Turk study, we developed and trained an objectivity classifier which performed better than prior proposed lexicons from literature. (4) Believability Computation: We developed FactChecker, a truth-finding method that linearly combines objectivity and co-mention influence. Our experiments showed that FactChecker outperforms prior methods."

>	"From these results we make the following observations: i) Majority vote is a competitive baseline; ii) Iterative voting-based methods provide slight improvements on majority vote. This is due to the fact that at the core of iterative voting is still the assumption that fact candidates mentioned in many sources are more likely to be true. Therefore, for both majority vote and iterative voting, when mention frequencies of various alternatives are the same, accuracy suffers. Based on these observations, it is clear that truthfinding solutions need to incorporate fine-grained content-aware features outside of external votes. FactChecker takes a step in this direction by incorporating the document-level feature of objectivity."

>	"There is a fairly small body of work on truthfinding. The method underlying most truth-finding algorithms is iterative transitive voting. Fact candidates are initialized with a score. Trustworthiness of sources is then computed from the believability of the fact candidates they mention. In return, believability of candidates is recomputed based on the trustworthiness of their sources. This process is repeated over several iterations until convergence. (Yin et al., 2007) was the first to implement this idea, subsequent work improved upon iterative voting in several directions. (Dong et al., 2009) incorporates copying-detection; giving high trust to sources that are independently authored. (Galland et al., 2010) approximates error rates of sources and fact candidates. (Pasternack and Roth, 2010) introduces prior knowledge in the form of linear programming constraints in order to ensure that the truth discovered is consistent with what is already known. (Yin and Tan, 2011) introduces supervision by using ground truth facts so that sources that disagree with the ground truth are penalized. (Li et al., 2011) uses search engine APIs to gather additional evidence for believability of fact candidates. WikiTrust (Adler and Alfaro, 2007) is a content-aware but domain-specific method. It computes trustworthiness of wiki authors based on the revision history of the articles they have authored. Motivated by interpretability of probabilistic scores, two recent papers addressed the truth-finding problem as a probabilistic inference problem over the sources and the fact candidates (Zhao et al., 2012; Pasternack and Roth, 2013). Truth-finders based on textual entailment such as TruthTeller (Lotan et al., 2013) determine if a sentence states something or not. The focus is on understanding natural language, including the use of negation. This is similar to the goal of fact extraction."


#### Platanios, Blum, Mitchell - ["Estimating Accuracy from Unlabeled Data"](http://auai.org/uai2014/proceedings/individuals/313.pdf)
>	"We consider the question of how unlabeled data can be used to estimate the true accuracy of learned classifiers. This is an important question for any autonomous learning system that must estimate its accuracy without supervision, and also when classifiers trained from one data distribution must be applied to a new distribution (e.g., document classifiers trained on one text corpus are to be applied to a second corpus). We first show how to estimate error rates exactly from unlabeled data when given a collection of competing classifiers that make independent errors, based on the agreement rates between subsets of these classifiers. We further show that even when the competing classifiers do not make independent errors, both their accuracies and error dependencies can be estimated by making certain relaxed assumptions. Experiments on two real-world data sets produce estimates within a few percent of the true accuracy, using solely unlabeled data. These results are of practical significance in situations where labeled data is scarce and shed light on the more general question of how the consistency among multiple functions is related to their true accuracies."

>	"Estimating accuracy of classifiers is central to machine learning and many other fields. Traditionally, one estimates accuracy of a function based on its performance over a set of labeled test examples. This paper considers the question of under what conditions is it possible to estimate accuracy based instead on unlabeled data. We show that accuracy can be estimated exactly from unlabeled data in the case that at least three different approximations to the same function are available, so long as these functions make independent errors and have better than chance accuracy. More interestingly, we show that even if one does not assume independent errors, one can still estimate accuracy given a sufficient number of competing approximations to the same function, by viewing the degree of independence of those approximations as an optimization criterion. We present experimental results demonstrating the success of this approach in estimating classification accuracies to within a few percentage points of their true value, in two diverse domains."

>	"We consider a “multiple approximations” problem setting in which we have several different approximations, to some target boolean classification function, and we wish to know the true accuracies of each of these different approximations, using only unlabeled data. The multiple functions can be from any source - learned or manually constructed. One example of this setting that we consider here is taken from NELL. NELL learns classifiers that map noun phrases to boolean categories such as fruit, food and vehicle. For each such boolean classification function, NELL learns several different approximations based on different views of the NP. One approximation is based on the orthographic features of the NP (e.g., if the NP ends with the letter string “burgh”, it may be a city), whereas another uses phrases surrounding the NP (e.g., if the NP follows the word sequence “mayor of”, it may be a city). Our aim in this paper is to find a way to estimate the error rates of each of the competing approximations, using only unlabeled data (e.g., many unlabeled NPs in the case of NELL)."

>	"The main contributions of this paper include: (1) formulating the problem of estimating the error rate of each of several approximations to the same function, based on their agreement rates over unlabeled data, as an optimization problem, (2) providing two different analytical methods that estimate error rates from agreement rates in this setting, one based on a set of simultaneous equations relating accuracies, agreements, and error dependencies, and a second, based on maximizing data likelihood, and (3) demonstrating the success of these two methods in two very different real-world problems."

>	"We have introduced the concept of estimating the error rate of each of several approximations to the same function, based on their agreement rates over unlabeled data and we have provided three different analytical methods to do so: the AR method, the MLE method and the MAP method. Our experiments showed that the AR method performs significantly better than the other two methods for both data sets we considered. Our results are very encouraging and suggest that function agreement rates are indeed very useful in estimating function error rates. We consider this work to be a first step towards developing a self-reflection framework for autonomous learning systems. There are several directions we would like to pursue to further improve upon the methods introduced here. Firstly, we wish to explore other interesting natural objectives one can aim to optimize. It would also be very interesting to explore possible generalizations of our models to non-boolean, discrete-valued functions, or even to real-valued functions. Finally, apart from simply estimating function error rates, we want to explore how the obtained error rate estimates can be used to improve the learning ability of a system such as NELL, for example. In this context, we could try using our estimates in order to develop a more robust co-training framework. One very direct application of our methods would be to use the estimated error rates and their dependencies in order to combine the functions’ outputs and obtain one final output."

  - https://youtu.be/PF6ViL5pcGs?t=5m3s


#### Samadi, Talukdar, Veloso, Blum - ["ClaimEval: Integrated and Flexible Framework for Claim Evaluation Using Credibility of Sources"](http://www.cs.cmu.edu/~mmv/papers/16aaai-claimeval.pdf)
>	"The World Wide Web has become a rapidly growing platform consisting of numerous sources which provide supporting or contradictory information about claims (e.g., “Chicken meat is healthy”). In order to decide whether a claim is true or false, one needs to analyze content of different sources of information on the Web, measure credibility of information sources, and aggregate all these information. This is a tedious process and the Web search engines address only part of the overall problem, viz., producing only a list of relevant sources. In this paper, we present ClaimEval, a novel and integrated approach which given a set of claims to validate, extracts a set of pro and con arguments from the Web information sources, and jointly estimates credibility of sources and correctness of claims. ClaimEval uses Probabilistic Soft Logic, resulting in a flexible and principled framework which makes it easy to state and incorporate different forms of prior-knowledge. Through extensive experiments on realworld datasets, we demonstrate ClaimEval’s capability in determining validity of a set of claims, resulting in improved accuracy compared to state-of-the-art baselines."

>	"In this paper, we proposed ClaimEval, an integrated, flexible, and principled system for claim evaluation. In contrast to previous approaches for claim evaluation, given a set of claims, ClaimEval identifies a set of relevant sources and evidences within them which might support or refute the claims, estimates credibility of those sources, and uses those credibility estimates to evaluate correctness of the claims - all in a single integrated system. ClaimEval uses Probabilistic Soft Logic to flexibly incorporate various types of prior-knowledge from the user. Through extensive experiments on real-world datasets, we demonstrated ClaimEval’s effectiveness over other state-of-the-art baselines. As part of future work, we hope to exploit the flexibility offered by ClaimEval and incorporate other types of prior-knowledge and user preferences and evaluate their effect on claim evaluation."



---
### interesting papers - multimodal knowledge representation

#### Jabri, Joulin, Maaten - ["Revisiting Visual Question Answering Baselines"](http://arxiv.org/abs/1606.08390)
>	"Visual question answering is an interesting learning setting for evaluating the abilities and shortcomings of current systems for image understanding. Many of the recently proposed VQA systems include attention or memory mechanisms designed to perform "reasoning". Furthermore, for the task of multiple-choice VQA, nearly all of these systems train a multi-class classifier on image and question features to predict the answers. This paper questions the value of these common practices and develops a simple alternative model based on binary classification. Instead of treating answers as competing choices, our model receives the answer as input and predicts whether or not an image-question-answer triplet is correct. We evaluate our model on the Visual7W Telling and the VQA Real Multiple Choice tasks, and find that even simple versions of our model perform competitively. Our best model achieves state-of-the-art performance of 65.8% on the Visual7W Telling task and competes surprisingly well with the most complex systems proposed for the VQA Real Multiple Choice task. Additionally, we explore variants of our model and study the transferability of our model between both datasets. We also present an error analysis of our best model, the results of which suggests that a key problem of current VQA systems lies in the lack of visual grounding and localization of concepts that occur in the questions and answers."


#### Andreas, Rohrbach, Darrell, Klein - ["Deep Compositional Question Answering with Neural Module Networks"](http://arxiv.org/abs/1511.02799)
>	"Visual question answering is fundamentally compositional in nature - a question like 'where is the dog?' shares substructure with questions like 'what color is the dog?' and 'where is the cat?'. This paper seeks to simultaneously exploit the representational capacity of deep networks and the compositional linguistic structure of questions. We describe a procedure for constructing and learning neural module networks, which compose collections of jointly-trained neural “modules” into deep networks for question answering. Our approach decomposes questions into their linguistic substructures, and uses these structures to dynamically instantiate modular networks (with reusable components for recognizing dogs, classifying colors, etc.). The resulting compound networks are jointly trained. We evaluate our approach on two challenging datasets for visual question answering, achieving state-of-the-art results on both the VQA natural image dataset and a new dataset of complex questions about abstract shapes."

>	"In this paper, we have introduced neural module networks, which provide a general-purpose framework for learning collections of neural modules which can be dynamically assembled into arbitrary deep networks. We have demonstrated that this approach achieves state-of-the-art performance on existing datasets for visual question answering, performing especially well on questions answered by an object or an attribute. Additionally, we have introduced a new dataset of highly compositional questions about simple arrangements of shapes, and shown that our approach substantially outperforms previous work. So far we have maintained a strict separation between predicting network structures and learning network parameters. It is easy to imagine that these two problems might be solved jointly, with uncertainty maintained over network structures throughout training and decoding. This might be accomplished either with a monolithic network, by using some higher-level mechanism to “attend” to relevant portions of the computation, or else by integrating with existing tools for learning semantic parsers. The fact that our neural module networks can be trained to produce predictable outputs - even when freely composed - points toward a more general paradigm of “programs” built from neural networks. In this paradigm, network designers (human or automated) have access to a standard kit of neural parts from which to construct models for performing complex reasoning tasks. While visual question answering provides a natural testbed for this approach, its usefulness is potentially much broader, extending to queries about documents and structured knowledge bases or more general signal processing and function approximation."

  - http://research.microsoft.com/apps/video/default.aspx?id=260024 (Darrell, 10:45)


#### Xu, Ba, Kiros, Cho, Courville, Salakhutdinov, Zemel, Bengio - ["Show, Attend and Tell: Neural Image Caption Generation with Visual Attention"](http://arxiv.org/abs/1502.03044)
>	"Inspired by recent work in machine translation and object detection, we introduce an attention based model that automatically learns to describe the content of images. We describe how we can train this model in a deterministic manner using standard backpropagation techniques and stochastically by maximizing a variational lower bound. We also show through visualization how the model is able to automatically learn to fix its gaze on salient objects while generating the corresponding words in the output sequence. We validate the use of attention with state-of-the-art performance on three benchmark datasets: Flickr8k, Flickr30k and MS COCO."

  - http://videolectures.net/deeplearning2015_salakhutdinov_deep_learning_2/ (Salakhutdinov, 12:19)
  - http://videolectures.net/icml2015_xu_visual_attention/
  - https://github.com/kelvinxu/arctic-captions




<brylevkirill (at) gmail.com>