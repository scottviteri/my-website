---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Be the Agi"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2023-02-04T11:54:02-07:00
lastmod: 2023-02-04T11:54:02-07:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

Crossposted at https://www.lesswrong.com/posts/FnfAnsAH6dva3kCHS/research-direction-be-the-agi-you-want-to-see-in-the-world.

Be the AGI you want to see in the world.

Epistemic status: highly speculative, authors are not neuroscientists.
# Summary

 - It may be possible to enhance human intelligence via a brain-computer interface (BCI). We could put electrodes into a human brain, connect those electrodes to an artificial neural network, and train that network to predict and write neural activations.
 - This may present a technique for gradual uploading of human minds to computers that doesn’t require technology sufficient to create AGI in the first place.
 - The purpose of this article is to elicit feedback on this idea and, if it seems promising, encourage more work in this area.

# Introduction: Goal and Idea
## Goal

We suspect that it may be possible to develop an enhancement system for human brains which satisfies the following desiderata:

1. Competitiveness: Our enhancement system must be powerful enough to help humans escape the acute AGI risk period. This desideratum may be satisfied if enhanced humans are able to find a solution to the prosaic AI alignment problem.
2. Timeliness: Our enhancement system must be fully developed before the advent of AGI.
3. Value preservation: Our enhancement system must not severely distort the core values of the enhanced human.

## Idea

Human brains are sharply constrained in size. Indeed, human birth is difficult because our brains (and thus skulls) are [unusually large](https://en.wikipedia.org/wiki/Obstetrical_dilemma) compared to other primates.

If evolution progressed such that human brains evolved until it hit a size constraint, then it seems likely that further increasing human brain size would yield more than modest gains to human intelligence.

One possible approach to increasing human brain size is by predicting real-time activations in the neocortex. The guiding intuition is that this is already how the brain extends itself, like how the [cerebellum currently predicts activations in the telencephalon](https://www.lesswrong.com/s/HzcM2dkCq7fwXBej8/p/Y3bkJ59j4dciiLYyw#4_6__Short_term_predictor__example__1__The_cerebellum). Namely, Neuralink hardware currently supports [three thousand EEG probes](https://www.jmir.org/2019/10/e16194/PDF) which can read from the brain, and Neuralink has the intention to add write access as well. Write access in this context means that the Neuralink probes could pipe brain activation data into a neural network which is trained to predict future brain activations, and the write probes could send those predictions as signals back into the brain. Scott believes that other hypotheses such as [spike-timing dependent plasticity](https://www.frontiersin.org/articles/10.3389/fncom.2010.00019/full) and [predictive coding](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2666703/) further support the hypothesis that the brain will learn to harness predictive signals from the EEG probes.

Human brains are optimized for low energy [expenditure rather than speed](https://www.semanticscholar.org/paper/Cognitive-systems-optimize-energy-rather-than-Markman-Otto/bc0c4e091933fd00d17d0df0bd64247ae7d237aa), and it can take [tens of milliseconds](https://academic.oup.com/cercor/article/14/8/851/268309) for a single serial communication between neurons. Artificial neural networks could run faster. For instance, if a language model the size of Chinchilla could predict neural activations, then current neural network hardware could speed serial computations in the brain by two orders of magnitude (0.7ms to 70ms, of course depending on the distance between the neurons).

However, 3e3 probes is essentially nothing in the context of a brain with 8e10 neurons. To keep the orders of magnitude consistent, this is like expecting to read and predict 10 or 100 activations out of a neural network with 100M. Our core hypothesis is that this is not the correct neural network analogy: since both the neural prosthesis and your brain are simultaneously learning, it is more like jointly training the two networks. In this setting, the loss could flow into the helper network through the EEG probes, and the main network could learn to supply inputs to the helper network such that it is especially helpful. For instance, if the Neuralink network has access to a compass, the internet, or 4D-shape rotation software, the brain could potentially learn to take advantage of the new hardware.

So suppose we could wire into a computational substrate in this way. Then not only could we get access to new senses, but also we might discover an increase in raw processing ability. One might experience this as a speed up of serial computation in the brain, resulting in substantial improvements in intelligence.

This architecture seems highly scalable. Indeed, any advancement in the general class of predictive computers could be leveraged to improve our brain state predictor. If humans could stay roughly competitive with AI for longer, then humanity would have a better shot at survival into the long term future. An additional win condition here would involve enough modeling of the brain's dynamics that we could essentially use this as an incremental uploading procedure.

# Details on competitiveness
## Method

Since we are bandwidth constrained, it may make sense to start out with a helper network that has been pre-trained on other brain data and/or the internet. But there is some reason to believe that predicting brain activations might be feasible even without pre-training, or the brain rerouting to make use of the helper network.

First, let's Fermi estimate how much data we might need to predict neural activations. Maybe predicting sufficiently dense probes in the visual cortex is analogous to predicting next pixels on YouTube, and predicting sufficiently dense probes in Broca's area is analogous to predicting the next word. Let's naively assume that we need as much data as was used to train GPT3 Davinci, which used [570GB](https://arxiv.org/pdf/2005.14165.pdf) (around 5.7e11 bytes or 5e12 bits) of text data after filtering. Suppose we read from 3e3 neurons. Each reading is in the form of a boolean array of length 3e3, denoting whether that neuron is currently undergoing an activation potential. Let's take the readings 10 times per second to reduce correlation, giving us 3e4 bits/seconds. So we need 5e12 bits / 3e4 bits/sec ~ 1.7e8 seconds = 17 years. So this would need an order of magnitude improvement in the (very preliminary) Neuralink probe count or an order of magnitude improvement in data efficient of neural networks to be feasible.

Some ways in which this could be false:

1. Predicting insufficiently dense probes is akin to predicting a single random pixel on YouTube -- this could be much harder than the original task, since we don't have direct access to global information in the image
2. Concepts in the brain are not fixed to neurons, but rather might move around faster than continual helper network learning can keep up with (again we are really not neuroscientists)

One reason to believe that 3,000 faster neurons could meaningfully help your cognition is that the current state-of-the-art artificial neural networks have hidden dimension only [~10,000 neurons wide](https://arxiv.org/pdf/2005.14165.pdf#page=8) (d_model), and can do very impressive things (e.g. strongly superhuman Go play, roughly human-level language abilities, memorizing large amounts of knowledge on the internet).

Even in the case of an unlearnable signal, it is possible to get partial credit. GPT3 probably has some human-like conceptual structures since it was trained on so much human-generated, information-bearing signal. We could imagine just adding more human-generated data -- EEG, iEEG, fMRI, YouTube, Spotify, speech and movement data, eye tracking data, etc. Reinforcement learning from human feedback also jams more human information into the model. For relevant information for this idea, see Gwern's post https://www.reddit.com/r/reinforcementlearning/comments/9pwy2f/wbe_and_drl_a_middle_way_of_imitation_learning/.

Some particularly relevant examples:

1. [Low-dimensional Embodied Semantics for Music and Language](https://arxiv.org/abs/1906.11759)
2. [Interpretable Semantic Vectors from a Joint Model of Brain- and Text-Based Meaning](https://www.cs.cmu.edu/%7Eafyshe/papers/acl2014/jnnse_acl2014.pdf)
3. [Exploring Semantic Representation in Brain Activity Using Word Embeddings](https://aclanthology.org/D16-1064.pdf)

These at least provide evidence for the possibility of using fMRI data, which provides spatially coarse (typically [3-4 mm](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3073717/)) read access, but not write access. Even if we used a different kind of write access in conjunction with fMRI reading, the authors suspect that predicting fMRI data would not yield sufficiently detailed modeling of human cognition. Also, some of these papers talk about tracking the contents of attention (usually via eye movement and surface electrodes). Anecdotally, humans seem to fruitfully exploit low bandwidth channels by tracking each others' attention.

In the scenario where we do not have enough direct write access, we could harness auxillary pathways such as projecting information onto a Google glass equivalent or via a [vest with targeted vibrations](https://eagleman.com/science/sensory-substitution/), potentially using a joint brain-image embedding space trained similarly to [CLIP](https://arxiv.org/abs/2103.00020). [Here](https://www.sciencedirect.com/science/article/pii/S0306452221000129) is an example of gaining hearing abilities through a vibrating wristband. The key challenge here is that the brain may be slow to learn to use this new signal. For example, it generally takes an adult [4 months](https://blindlowvision.org.nz/information/braille/learning-braille/#:~:text=Like%20any%20new%20skill%2C%20braille,ve%20got%20it%20for%20life.) to learn braille, and predicted brain data would be a much more complicated signal. It took 1 month for vibrating wristband users to distinguish between three sounds with 70% average accuracy.

A key aspect of competitiveness is that humans cannot be expected to think as quickly as future AI's if any part of the human is running on a biological neuron substrate. The authors imagine that adding more predictive capacity and bandwidth will lead to more and more of the human being implemented on the computer. At this point, perhaps the ML predictive model will contain enough of you that transitioning to fully digital would be more like a software port between between ruby and python than a full rewrite. The authors hope that this can be done in such a way to provide continuity of self. Much more research is needed here to flesh out what such a transition might look like. Continuity of self seems more tenuous without direct write access to the brain, even with indirect neural predictions such as through the visual system.

## Current state of the technology

As mentioned earlier, Neuralink currently has the capability to read from [three thousand neurons](https://www.jmir.org/2019/10/e16194/PDF). The status of write access is unclear --  [the paper says](https://www.jmir.org/2019/10/e16194/PDF#page=10):

    Modulating neural activity will be an important part of next-generation clinical brain-machine interfaces [39], for example, to provide a sense of touch or proprioception to neuroprosthetic movement control [40,41]. Therefore, we designed the Neuralink ASIC to be capable of electrical stimulation on every channel, although we have not demonstrated these capabilities here.

Existing solutions can both read and write with [128 electrodes](https://www.nature.com/articles/s41551-018-0323-x).

[Zhao et al](https://www.nature.com/articles/s41551-022-00941-y) recently harnessed advances in electrode probe flexibility to stably record 1000 neurons in a regular grid over 1 cubic millimeter.

Many other brain measurement technologies exist besides electrodes, but electrodes are especially nice because they offer high spatial (10s of micrometers) and temporal (ms) resolution.

Some EEG signals are predicted in [Modern Machine Learning as a Benchmark for Fitting Neural Responses](https://www.frontiersin.org/articles/10.3389/fncom.2018.00056/full) but it is from 2018 and uses LSTM's, so it would be interesting to see how accurately we can do prediction on https://github.com/KordingLab/spykesML.

[Self-Supervised Learning of Brain Dynamics from Broad Neuroimaging Data](https://arxiv.org/pdf/2206.11417.pdf) predicts fMRI signals via pre-training on [OpenNeuro.org](https://openneuro.org/) and [Human Connectome Project](https://wiki.humanconnectome.org/display/PublicData/How+to+Access+Data+on+ConnectomeDB) datasets. This model achieves an F1 score of 0.9 on the downstream task of predicting mental states such as story-telling vs math, fear vs neural, and left vs right finger.

# Details on alignment

In the extreme, this is a post about brain uploading, values and all. To avoid the failure mode of uploading your least favorite person, it may be possible to upload large numbers of people if this technology is sufficiently scalable. While Neuralink has automated the surgical process to allow greater scaling, many people are likely to gawk at the notion of invasive surgery. Fortunately, there are a whole spectrum of possible merging techniques possible, from Neuralink to fine-tuning a language model on your own speech and writing.

But the farther we are from Neuralink on this spectrum, the more suspect the alignment properties. Even within the Neuralink story, alignment might depend on details of the training procedure. If the prediction is trained from scratch, then it may be analogous to simply having more brain. But if, for sample efficiency reasons, the neural activations are first embedded into a pre-trained language model's latent space, a person's internal models may end up distorted. We might be able to mitigate this concern by using contrastive learning to encode the Neuralink user's brain activations into a joint latent space with internet text. We would welcome theory work to understand how these and other options affect alignment properties.

# Future Work

1. Run main and helper neural networks and see how many connection points are needed to improve performance
   a. Try this with and without training the helper and main networks jointly
   b. See how the difficulty of prediction changes as a function of the distance between the inputs and outputs of the helper network
2. Find online repositories of EEG data and experiment to check the difficulty of the prediction task
   a. Check the usefulness of pre-training in this regime
3. [Dishbrain](https://www.nature.com/articles/d41586-022-03229-y) is the name of an experiment where a plate of biological neurons learned to play pong in five minutes by controlling the paddle height with spiking patterns. We would like to know if neural predictions would allow the neurons to learn the game more quickly.

The authors would like to thank [@Adam Shai](https://www.lesswrong.com/users/adam-shai?mention=user) and [@Steven Byrnes](https://www.lesswrong.com/users/steve2152?mention=user) for feedback on earlier drafts, as well as Joscha Bach, [@Garrett Baker](https://www.lesswrong.com/users/d0themath?mention=user), [@NicholasKees](https://www.lesswrong.com/users/nicholaskees?mention=user), [@Erik Jenner](https://www.lesswrong.com/users/erik-jenner?mention=user), Rylan Schaeffer, and Victor Lecomte for fruitful conversations.
