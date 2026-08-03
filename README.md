*"All models are wrong, but some are differentiable."*

```julia
# Ultra-barebones Bootstrap PF
using Random, Distributions, Transducers, StatsBase
Random.seed!(8675309)

T, N = 100, 1000

x = accumulate(+, randn(T))
y = x .+ randn(T)

f(x) = x + randn()
g(y, x) = pdf(Normal(x, 1), y)

step(x, y) = (x = f.(x); sample(x, Weights(g.(Ref(y), x)), N))
particles = y |> Scan(step, randn(N)) |> collect
```
## ❤️ Hello ❤️

You have found my GitHub 😁

I am Dr. Ben(jamin) Cox, and I am a computational statistician. My background is in spatio-temporal Bayesian signal processing (in particular, particle filters and parameter inference therein). I did my PhD in statistics at the University of Edinburgh. I now work at the Max Planck Institute for Physics and am loosely associated with the MADMAX and LEGEND groups here. 

My current work is funded by Germany’s Federal Ministry of Research, Technology and Space (BMFTR) within the ErUM-Data programme under grant FKZ 05D25PC1 (DEMOS consortium).

I primarily speak Python and Julia, but some C, C++, and Rust has managed to worm through my defences. I used to speak R, MATLAB, and Fortran, but less so these days.

Other languages include: native English, Deutsch at A2 CEFR (allegedly, doesn't feel like it), Russian (did an A-level in it, was at B1 equivalent circa 10 years ago)

My interests outside of work (that you will see scant evidence of here) include:
- Ballet (Russian, relearning)
- Custom hardware
  - medication thumper because I forget my patches constantly
  - divergence meter à la Steins;Gate (driven by a local sentiment model to compute a facsimile of divergence, using LED 'nixie' tubes because HV scares me)
  - mini eink note taking device
- Riflery (if you know a good club in the Munich area let me know)
- Mountaineering (need to get back in shape 😒)

### Currently looking for collaborators:
- FlatPPL: probabilistic programming language developed with physics use cases as first class. The language describes a DAG encoding the model - this can be a likelihood, a posterior density, or a random sample. It quite intentionally does not encode analyses or algorithms - it is designed to hook in to a host language for these. If you are interested in getting involved, please drop me and/or Dr. Schulz an email. Currently in early development.

### Ongoing side quests:
- Deutsch lernen
- Physics
- Whatever ML projects I cook up in my spare time (trees ftw)
- Programming for GPU (so as to tailor methods towards this paradigm, e.g. branchless and fixed working memory)

### Ask me about:
- Time series modelling
- Probabilistic programming
- Particle filters
- Discworld
- Evangelion (original, not rebuilds😅)
- My on again off again relationship with JAX
- The clear unambiguous theoretical superiority of Bayesian statistics and why it often does not work out in practice

### Contact:
- Email (work): bcox@mpp.mpg.de
- Email (personal): bjm.cox@posteo.de

### Pronouns:
they/them at this time, although living in Germany makes this hard 🥲 - if you are feeling kind lean towards sie (or just use my name) 😊. I am not in the habit of correcting people on this, however. 


<!--
**BJMCox/BJMCox** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
