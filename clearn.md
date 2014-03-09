---
layout: article
title: Concept Learning
---

# Concept Learning
subtitle here

## Introduction

At present we cannot fully account for the ease with which humans apprehend new concepts. We are presented with such apparently sparse and incomplete data, yet we still form robust mental models that allow us to give rich structure to what we experience in the world. Our learning ability seems to violate a priori constraints on what can be inferred from only so much data. If we recognize that we have too little data to support an inference, the only way out is to realize that there is more information than we are accounting for. The question is how this is true.  We are interested in investigating this phenomenon for many reasons, among them being how it would inform our attempts to endow machines with human-like intelligence and the implications it could have in treating learning disorders and improving pedagogical practices. By viewing problems of induction and inductive learning as computational problems, we can use new methods of neurobiological data collection (i.e. fMRI) to probe learning phenomena at a basic level. The fast-mapping of words to objects by a toddler, for instance, can be interpreted as a computation performed on the sensory data received by the toddler.

A useful computation around which much study is centered is that of word learning - the mapping of words to concepts or objects - in children. Word learning models lend themselves easily to both experimentation and generalization to other conceptions of learning. Word learning models that have been applied in the past are often defined by their approach to the structure of pre-existing knowledge and the structure of inference, as well as the relationship between the two. A very simple model in the case of word learning is that of hypothesis elimination, in which positive pairings of words to objects support a plausible hypothesis space and negative pairings reduce this hypothesis space. Such a process is, in other words, deductive. Connective or associative theories of learning describe a complex structure of inference that grows with new data - often represented by a neural network with many hidden layers. Nativist theories, in contrast, place some prior structure and/or content in knowledge and describe computations performed with these pre-existing structures. As we will see, however, none of these models have yet encompassed all characteristics of word learning as observed in humans.

##Bayesian Models of Cognition

Joshua Tenenbaum of MIT has been investigating Bayesian models of cognition as an alternative to many of the previously mentioned older approaches. Tenenbaum's study is centered around three questions about abstract knowledge \cite{tenenbaum2011}:

> (1) How does abstract knowledge guide learning and inference from sparse data?
> (2) What forms does abstract knowledge take, across different domains and tasks?
> (3) How is abstract knowledge itself acquired?

Tenenbaum’s Bayesian model focuses on accounting for two things: learning concepts and learning causal relationships. It does this by having “richly structured, expressive knowledge representations (2) with powerful statistical inference engines (questions 1,3)." This distinguishes the Bayesian model from the other models mentioned above - a connectivist model requires a powerful statistical inference engines (questions 1,3)  without inherently structured knowledge, whereas a nativist knowledge depends on a structured knowledge (2) with only a relatively simple method of statistical inference.

Bayesian reasoning is govern by a commonly-cited theorem for probabilistic reasoning, where the probability of event $A$ given observation B is the likelihood of the observed $B$ at $A$ weighted by a prior probability of A:

$$ P(A \vert B) = \frac{P(B \vert A)P(A)}{P(B)} $$

Tenenbaum gives an example of the seemingly natural relation between Bayesian reasoning and human learning by noting how neatly Bayesian reasoning fits the way children learn the meanings of new words with such ease, a problem that’s been discussed at great length. Paraphrasing the statement of the problem in his paper, suppose a child is presented with pictures of three horses and is told “horse” \cite{tenenbaum2011}. The child could in principle conclude that “horse” means “all horses except Clydesdales”, “all four-legged animals”, “all horses with black spots on their face”, “all non-Clydesdale horses presented only in a picture” etc. The way out under a Bayesian model of learning is that the child is able to infer the correct meaning because she has acquired generalized priors that have taught her that inferring the “basic category”, i.e. associating new words only with salient features of the reference pairings, is often the correct choice. This can be formalized by thinking of the child as using Bayes’s theorem to inform her personal probabilities for possible hypotheses $h_{1}, h_{2}, ..., h_{n}$. The child uses her “statistical inference engine” to heavily favor that $h_{a}$ which seems most likely to pick out only the most salient features, i.e. that which fits with her experience of successful associations. Further, the child might recognize, with other priors, that it would be a “suspicious coincidence” if the three animals were horses but the word “horse” meant animal. This is very important for the Bayesian cognitive model, as it informs decisions about the specificity of the meaning the word is being mapped to.

Tenenbaum empirically tested his hypothesis by recreating similar situations with children \cite{tenenbaum2007}. He presented children with pictures of objects and told them their ‘names’ (blick, fep, dax) in an imaginary language (Tenenbaum, 2007), with both 1-picture and 3-picture trials. The 3-picture trials sometimes formed a subcategory (Dalmatian), sometimes a basic category (dog), and sometimes a supercategory (animal) - together forming a system of taxonomic constraint. He then coaxed the children to choose objects they deemed to be feps, blicks, or daxes and noted when they picked at a subcategory, a basic level, or a higher level.

The results were consistent with what would be expected of a cognitive model operating with Bayesian principles. The patterns of what children chose in certain situations lined up reasonable error with what a purely Bayesian model would have predicted: in line with the “suspicious coincidence” principle children rarely inferred a basic-level category when presented with subcategorical objects and rarely inferred supercategories when presented with basic-level objects. 

Looking back at the alternative word-learning models presented at the start of this section, some of their shortcomings may now be apparent. In general, some of these models fail to explain why a child's performance got better better when presented with 3 objects instead of 1. 

Tenenbaum explains that the hypothesis elimination model runs aground because the model dictates that in the 1-object case the child “opts for the basic-level category” (remembering that hypothesis elimination models do not have access to priors that would allow a child to learn to do this) but in the 3-object case it chooses “at the most appropriate level given the input”. The case-by-case definition of what happens cognitively in this model is very unattractive.

The associative or connectivist model has trouble explaining why a child’s response would be different for 1 vs. 3 objects in the subcategory case, e.g. 1 vs. 3 Dalmatians, as there is virtually no new information that would constrain hypotheses offered by having two more instances of the same relation.

The results of this empirical study make us hopeful for the success of Bayesian models of learning as they demonstrate fairly convincingly that humans are endowed with rich inferential mechanisms which traditional models have not captured enough. We have primarily discussed questions (1) and (3) so far, which have to do with how humans first acquire abstract knowledge (like the priors that predispose us to certain choices) and then use it to acquire new concepts. At this point, the discussion of word learning can be expanded to encompass a greater question of concept learning: How can a child presented with an incomplete, noisy grammar (i.e. the speech of parents and other caretakers) produce an infinitive generative grammar?

## Poverty of the Stimulus; The Anaphoric One
This discussion of grammar acquisition will begin with a particular construct termed the ``anaphoric \emph{one}''. 
will put summary from paper #15

##Adaptive Resonance Theory
will put summary from paper #17/18

## Conclusion

need to write!