---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Markovian Agents for Informative Language Modeling"

authors: [Scott Viteri, Max Lamparth, Peter Chatain and Clark Barrett]

date: 2024-05-23T21:08:09-08:00
# doi: "https://doi.org/10.1016/j.cognition.2022.105120"

# Schedule page publish date (NOT publication's date).
# publishDate: 2023-08-22T00:08:09-08:00

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["3"]

# Publication name and optional abbreviated publication name.
publication: "Arxive"
publication_short: "<i>Arxiv</i>"

abstract: "Chain-of-Thought (CoT) reasoning could in principle enable a deeper understanding of a language model's (LM) internal reasoning. However, prior work suggests that LMs can answer questions similarly despite changes in their CoT, suggesting that those models are not truly using the CoT. We propose an reinforcement learning technique to produce CoTs that are sufficient alone for predicting future text, independent of other context. This methodology ensures that if the LM can predict future tokens, then it must have used the CoT to understand its context. We formalize the informativeness of a sender to a receiver LM as the degree to which the sender helps the receiver predict their future observations, and we define a 'Markovian' LM as one which predicts future text given only a CoT as context. We derive a 'Markovian training' procedure by applying our definition of informativeness to a Markovian LM and optimizing via policy gradient and Proximal Policy Optimization (PPO). We demonstrate our training algorithm's effectiveness on fifteen-term arithmetic problems, show the model utilizes the CoT, and externally validate that the generated CoT is meaningful and usable by another model. "

# Summary. An optional shortened abstract.
summary: ""

tags: []
categories: []
featured: true

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_pdf: "https://arxiv.org/abs/2404.18988"
url_code: "https://github.com/scottviteri/MarkovianTraining"
url_dataset:
url_poster:
url_project:
url_slides:
url_source:
url_video:

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---

<span>&#42;</span> indicates equal contribution, <span>&#8224;</span> indicates co-corresponding authors.
