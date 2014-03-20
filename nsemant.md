---
layout: article
title: Neurosemantics
---

Neurosemantic Word Representation
=================================

Scientific inquiry into the how concepts like *apple, honor, father, one*, etc. are represented in the mind has only recently become possible. New imaging machines and analysis methods from machine learning have both allowed neuroscientists to begin to investigate exactly how regions of the brain are responsible for encoding these concepts.

The scope of investigation has mostly been restrained to *concrete* nouns, which refer to physical objects in the world, such as *celery, car, mouse,* and *house*. This was deliberate, as *a priori* we might assume that this category is most basic. Once concrete nouns are better understood, the hope is that we will be better equipped to investigate (a) compound nouns (*bird tape*), (b) abstract nouns (*shame*), (c) predications (*the coffee is cold*), etc.

Explicitly, inquiry in neurosemantics attempts to answer these questions, as described by Mitchell (2008):

> What is the predicted fMRI neural activity encoding word w?
>
> What is the basis set of semantic features and corresponding components of neural activation that explain the neural activations encoding meanings of concrete nouns?

Mapping Between Observed Neural Activity and Semantic Dimensions
----------------------------------------------------------------

In this domain, researchers have spent most of their energy trying to understand how neurological data can be processed to yield semantic dimensions of a word and, in reverse, how semantic dimensions of a word can be used as predictors of observed neural activity. Neurological data takes the form of activity measured by an imaging instrument, and semantic dimensions can be thought of as “associational weights” or “how much word \(x\) has to do with subject \(y\)”.

In the studies we are considering here, researchers provided subjects with stimuli in the form of cues for concrete nouns, either as pictures or letters. They then obtained raw data of neural activity using an fMRI, MEG, or EEG and “cleaned” them up.[1]

There are two steps involved in moving from “cleaned-up” data to semantic information: feature extraction and classification .

Feature extraction involves somehow reducing the amount of the data to be considered. This is done in part because it reduces the computational cost of the classification task. This is important because considering all the data can easily make the data unanalyzable in a reasonable amount of time. Further, it has been shown, at least in some studies, that considering more data beyond a certain point does not significantly improve performance of analysis . Each study handles data differently, but broadly, the amount of data can be reduced in a couple of ways. Some studies reduced data by averaging over all sources[2] over large intervals like 50ms . Others left sampling rate high but manually set a limit on how many sources they collected data from, selecting only the most ‘informative’[3] ones . Once the data was cleaned and pared, neat vectors ready to be classified were left.

The classification task attempts to learn patterns in the neural data that correspond to the semantic properties of the noun. To this end standard machine learning techniques were employed, most common among them variations of support vector machines, linear regression, k-nearest neighbor, and Gaussian Na<span>ï</span>ve Bayes-pooled variance classifiers. The classifiers were often trained on a subset of all available data before being tested on the left-out data.

Simply, the classifier tries to learn a function \(f : X \rightarrow Y\) as best it can where \(X\) consists of the neural data and \(Y\) consists of the predicted semantic properties. Hence we note that we can use the inverse, \(f^{-1} : Y \rightarrow X\), to move from semantic properties to predicted neural data.

There’s a problem: neural data are readily observable, but how do we decide on semantic categories? Several approaches were used.

The first study we considered, Mitchell *et al.* (2008), used a technique from computational linguistics to approximate a word’s semantic features from collocations in a large corpus. Thus the assumption is that

> the semantic features that distinguish the meanings of arbitrary concrete nouns are reflected in the statistics of their use within a very large text corpus.

Testing trained classifiers against expected semantic values from analysis of a corpus, Mitchell *et al.* found, on the basis of success in moving from a word’s corporeal semantic features to predicted neural activity, that concrete nouns are associated with significant activity in both sensory-motor regions and non-sensory-motor regions.

A direct continuation of this study is Just *et al.* (2010). Instead of taking semantic categories for granted, factor analysis was used to isolate what came out to be just *three* brain groups from a selection of 60 concrete nouns that seemed to correspond to semantic properties having to do with eating, manipulability, and shelter. Further, using just brain activity in these three regions, semantic dimensions of an unknown word were able to be inferred with good accuracy. The inverse, moving from semantic dimensions of a word not in the training set to predict brain activity, was also done with good accuracy. That concrete nouns appear to *essentially* be parameterizations of only three factors is a very significant finding.

Further, the activation patterns for words encoded in these three parameters was found to correlate strongly with analogous values obtained from the latent semantic analysis technique employed on a large English corpus, giving us confidence that the parameters have significance.

A third study in this series, Sudre *et al.* (2012), engaged in a similar investigation, but this time with an MEG. MEG’s measure neural activity by detecting fluctuations in the magnetic field around the subject’s head caused by neural spikes. This means that they measure neural activity much more “directly” than fMRI’s, which gauge neural activity by observing blood oxygenation levels, which have a latency of 1000-2000ms. Thus fMRI’s have very poor temporal resolution. This is critical, as it may mean that we were missing information in the most early stages of neural activity after the stimulus.

The study did indeed find that the activation patterns in the earliest stages seemed to encode different semantic features than did later ones. They used as a ground truth for the corpus a database constructed using Amazon’s *Mechanical Turk* service consisting of answers to 218 “20 questions-style” questions about the same 60-word corpus from before such as “is it alive?” and “is it shiny?”. They then trained classifiers to decode semantic information at 50ms intervals. Critically, they found that perceptual (or sensory) features were decodable with the most accuracy in the 100ms-200ms interval while semantic features were most decodable in the intervals after 250ms. The study did find that the most decodable semantic features in this study could be grouped into features about animacy, manipulability, and size, which are similar to previous categories named shelter, manipulability, and eating from the earlier study. But it critically found that activation regions did not exactly match those of the 2010 study conducted with an fMRI.

The suggestion Sudre advances is that because the MEG is much more sensitive temporally, it was more sensitive to activity that would have been hard to measure with an fMRI. They further venture that the MEG was picking up “low level” information (the shape, size, feel of a screwdriver) vs. what the fMRI was measuring, “high level” information (screwing in a screw with a screwdriver, moving it with the hand). This hypothesis is advanced under the intuitive assumption that as time increases the mind considers more abstract features of the stimulus.

Another study we considered was Chan *et al.* (2012). Chan combined both MEG *and* EEG data from his subjects, being given stimuli comparable to those in previous studies, to investigate the effects of choice of modality on perceived brain activity. First, Sudre’s finding that MEG/EEG-mediated findings differed from fMRI-mediated findings was confirmed for the same reason advanced by Sudre: the poor temporal resolution of fMRI’s. Second, the study found that the EEG was much less useful in linking neural activity to semantic features, but Chan suggests that this may simply be due to the EEG having much fewer sensors. (The implication is that an EEG with just as many sensors as an MEG might produce comparable results.) He goes on to say, having observed that the EEG and MEG seem to access *different* semantic information, that

> neither recording modality is strictly superior to the other, and that EEG and MEG each provide unique information regarding neural processes.

Problems with assumptions
-------------------------

In Mitchell *et al.* (2008), the seminal paper in neurosemantics among those we reviewed, one key assumption is indicated which most research in the domain has been founded on:

> [The approach] assumes that the brain activity observed when thinking about any concrete noun can be derived as a weighted linear sum of contributions from each of its semantic features. Although the correctness of this linearity assumption is debatable, it is consistent with the widespread use of linear models in fMRI analysis (27) and with the assumption that fMRI activation often reflects a linear superposition of contributions from different sources.

This is a significant assumption. *A priori*, we can easily imagine that a weighted linear sum is *not* the only way the meaning of a concrete noun could be encoded. That is, we see no reason why a word’s semantic value must logically be a linear composite of neural intensity in different regions.

Further, we observed that an assumption that pervades the literature is that neural activity is positively correlated with how much the region of neural activity has to do with the mental task at hand. Could we imagine it otherwise? We may be tempted to entertain the thought that, for example, perhaps the brain could handle a task by *decreasing* or *changing the rhythm of* groups of neurons that are normally more active without a task.

So far these two assumptions have not outright failed researchers, but we may see them pushed to their breaking points in the future.

Conclusion
----------

Neurosemantic theory is in its infancy: it is hard to even call a ‘theory’ what might be more appropriately called a collection of observata. This line of inquiry is still only in its infancy, with approaches still being refined. Further, contemporary instruments, despite great advances, give data that is too noisy for even the best analytical techniques to produce near-perfect or even pretty good predictions. As such, we are still far from being able to “read minds” using these machines, as a cursory understanding of the literature might at first suggest.

But we do not wish to understate the accomplishments that have been made. These studies in neurosemantics have shown, for example, that the regions that encode semantic factors are mostly the same across people. Further, as we have seen, the studies have demonstrated somewhat convincingly that neural representations of concrete nouns can be understood as linear parameterizations of semantic factors. Further, it

There are many directions future research could take. Very many questions remain unanswered, among them being

[distributed vs. distributed-plus-hub vs. convergent zones, Mr. M]

outline big questions posed in Where do you Know What you Know? also actual relations between words

Neural Bases of Metaphors (16)

From Eardrum Vibrations to Semantic Dimensions (14)

[1] All techniques used to get brain data introduce artifacts which we want to remove before analysis. One example is the noise caused by the frequency at which AC power is provided: 60 Hz in the United States and 50 Hz most anywhere else. The details of what else is accounted for is beyond the scope of this review.

[2] “sources” here is a catch-all for the “atomic” part of a feature vector of a study, whether they’re readings of MEG/EEG channels or fMRI voxels.

[3] What this really means varies from study to study. For example, in , the voxels observed to be most stable were chosen.

