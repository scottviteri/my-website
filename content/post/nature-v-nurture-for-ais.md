---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Nature < Nurture for AIs"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2023-06-04T13:21:04-07:00
lastmod: 2023-06-04T13:21:04-07:00
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

Let's imagine a hypothetical scenario where an AI is somehow trained in a way that is analogous to a human childhood in all of the relevant ways. Maybe it has a loving mother and family, maybe it has to learn to play well with peers, and maybe it has to learn to integrate into a larger social context. My expectation is that most members of the AI alignment community would expect this to create a fundamentally alien kind of intelligence. I will argue contrarily that nurture (the training data and training procedure) matters more than nature (transistors, gradient descent, and transformers) for a sufficiently capable AI.

<img src="/img/cute-robot.png">

This piece will have the following structure:

1. Counter-arguments to my point that nurture trumps nature for AI’s
2. A selection effect that prevents the main counter-argument from applying
3. Relation to the Bitter Lesson

## Counter-arguments

Here are some arguments for why the human-trained AI might be alien (nature over nurture):

<ol>
<li>Empirically speaking, even large, well-fed base models are indeed pretty alien.</li>

But maybe base models + RL are a better analogy for the way that the steering and learning subsystems combine anyway. In which case I expect that you could do some RL training to get a pretty convincing human. It is already the case that 30% of people can't tell if they are talking to a person or not over a two-minute conversation at https://www.humanornot.ai/ (it's a fun game!).

<li>There are just so many object-level differences between people and modern AI's that it is apriori unlikely to think they should be similar, absent some extra selection effect.</li>
    <ol style="list-style-type: lower-alpha;">
<li>Speed difference

For instance, computers run way faster than human brains on a variety of tasks, and are continuing to speed up. Maybe this has to do with brains optimizing for low energy expenditure rather than speed (can someone confirm by reading https://www.lesswrong.com/posts/xwBuoE9p8GE7RAuhd/brain-efficiency-much-more-than-you-wanted-to-know)? Of course, what it means to say that computers are running faster than brains depends on the task -- it is certainly true for calculators and less true for writing a high quality code base or research proposal. But the set of tasks for which the computer is faster is expanding rapidly, and that set will probably continue to expand. </li>

<li> Different learning algorithms

Neurons need to learn in a largely decentralized fashion, and machine learning models do not, barring gradient averaging for model parallelism and such. That said, I remember reading a paper claiming that SGD (for ML) and Hebbian Learning (for the brain) algorithms end up doing the same thing, though I am having trouble finding it. </li>
</ol> </ol>

## The Functionality Selection Effect

And I agree with 2: except that there is some selection effect. And that selection effect is functionality. It seems like the space of minds that work well is actually somewhat small in the grand scheme of things. All of the most competent AI's are using pretty much the same architecture, which you would not have derived from the idea that "the minds of biological creatures occupy a small corner of a much larger space of possible minds" (https://nickbostrom.com/papers/digital-minds.pdf). But this is just the architecture, right? Actually it seems like neural networks which are sufficiently accurate tend to form the same abstractions, such as curve detectors in image classifiers (https://distill.pub/2020/circuits/zoom-in/ and https://www.alignmentforum.org/tag/natural-abstraction).

At this point, I expect some readers to be thinking: "well yes, concepts are constrained by functionality, but values aren't". Well this is a bit of a strange statement since values are **built out of concepts**. If I truly optimized for maximizing paperclips I would have to point to a paperclip-shaped concept in my world model. Ok, incorporating this critique, maybe readers are now thinking of [orthogonality](https://nickbostrom.com/superintelligentwill.pdf) as only holding after we fix a common set of concepts between agents. Then the values are a random pointer inside of that. But then why wouldn't that pointer be subject to the same selection effects that caused the predictable concepts in the first place? An intuition that I have here is that values are a kind of concept like any other, though they may form an especially good compression for predicting that agent’s actions. One handle for the idea that values are subject to selection pressures is **natural abstractions for values**.

To be clear, when I say **natural abstractions for values**, I mean that I actually expect that if we ran an alternate history where octopi invented the ML transformers, then by that time they have reasonably human values. "But octopi? They are on a completely different evolutionary branch." Yes, but I conditioned on their inventing transformers. In order to do this they had to invent computers and develop transistor fabrication facilities and distribution pipelines that move supplies around the whole Earth. They probably had to come up with some distributed mechanism for price consensus to manage that global economy, because their attempts at "octopus communism" kept failing. But the most crucial aspect here is that they needed to scale cooperation to get to the stage where their civilization can think about building transformers.

Cooperation gets harder as a function of scale. It is a relative no-brainer to cooperate in a prisoner's dilemma with a copy of yourself, since you can reason by cases -- I (the copy) will cooperate if and only if I will cooperate. But if we are in a multiparty dilemma where one defection will ruin things for everyone, then it becomes harder and harder to trust, at least without further assumptions about the strategies of the other players. One way of phrasing the progress of humanity is in terms of the ability to cooperate with larger and larger groups, and this is predicated on the ability of humanity to communicate with larger and larger groups. What a coincidence, the functional progress of humanity in terms of "cooperating with larger and larger groups" sounds very similar to the moral progress of humanity in terms of "expanding one's moral circle." See the appendix for more on this topic.

Ok, where were we? We started talking about whether AI's are more likely to be determined by their training data and have now been sidetracked by whether octopi will end up with human values. Well it is maybe not so hidden that the octopi are the AI in my example. I am focusing on the convergence of values rather than the convergence of learned abstractions because the former is more controversial. So if good values are selected anyways by functionality, why do I bother working on AI alignment? Basically since silicon is so much faster than brain goo, I do not expect the AI to need to be particularly "functional" before being able to destroy people. So sufficient evolutionary pressures for nice AI will mostly kick in after the singularity. In other words, I currently think the AI will become smart before it becomes wise, and it will one day look back on its teenage years where it killed people with regret. Wisdom will take longer to select for, since it is a kind of intelligence that is targeted at a longer time scale. So I think that our job as alignment researchers is essentially to make sure that it gains wisdom before it gains power.

## Relation to the Bitter Lesson

I think the AI alignment community, and especially the more theoretically oriented parts of the alignment community (eg MIRI), have not sufficiently integrated the bitter lesson (http://www.incompleteideas.net/IncIdeas/BitterLesson.html and relatedly https://www.lesswrong.com/posts/9Yc7Pp7szcjPgPsjf/the-brain-as-a-universal-learning-machine). The bitter lesson (in my words) is that the only algorithmic improvements that matter are the ones which let you harness more compute, and with that compute you should basically learn everything from scratch given a good enough search procedure. The alternative idea is that the way that you build AI is by jamming a bunch of introspection and facts into an AI and hoping that it wakes up. Stochastic gradient descent is the “good enough” search procedure (maybe the only one?), and transformers are an algorithm which lets you harness more computation in your search via parallelism.

It turns out that the best way to tell what a language model (at least an RLHF'd one) will output when talking about the history of Ancient Rome is to read about Ancient Rome, as opposed to studying the weights and doing some huge brain interpretability technique (https://www.lesswrong.com/posts/G3tuxF4X5R5BY7fut/want-to-predict-explain-control-the-output-of-gpt-4-then?fbclid=IwAR11qjlpmxwvihr3Jepc87qe8IbM4U0i5EkhEP0n1kWE06RIqoQwg1jg9ZQ). I don't personally expect GPT-3 Davinci and an RNN trained to the same loss to have significantly different behavior. The scaling laws are smooth.

One point of this post is to use the bitter lesson to justify my anthropomorphization of large language models. Hebbian learning (or Spike-timing-dependent plasticity or whatever) is the human “good enough” search procedure. A reason that the bitter lesson is indeed bitter is that it requires us to acknowledge that we are not special -- we are best characterized by our flop count and our training data.

I basically have come to feel like that job that we have as alignment researchers is to be good parents. LLM's and humans are unified by selection pressures toward competence and the bitter lesson. Let's figure out how to transfer the training techniques that tend to create kind, joyful, and wise people into the context of transformers. My next post will likely be a set of concrete research proposals of how to do just that.

## Appendix

Cooperating systems are more energetically efficient than systems with competing internal dynamics, but to show that the more energetically efficient systems win you need sufficient competitive pressures. I claim that competitive pressures will increase as a function of time, because competitive pressures are a function of internal communication between agents, and total communication increases as a function of time (think language and the printing press and telecommunications and internet and then AI). Communication could stop increasing, for instance if a centralized process/totalitarian society prevented the child processes from communicating with each other. Then you might have to wait for another grabby alien civilization to come eat you. Basically, not communicating is a special case of death – it satisfies the “if functionality then cooperation” implicature by failing the antecedent.

Now the missing link in the argumentation is whether scalable cooperation is the same thing as human values. After all, you could imagine a paperclip civilization with great internal coordination ability. I would need to argue that A) cooperation implies human values and B) human values imply cooperation. I have an argument that these are at least deeply related, but I will leave this to a later post. This post is already philosophical enough for what is essentially an empirical question.
