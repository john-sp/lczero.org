---
Title: "Forging Ahead: The T90 Series and Our Modernized Training Framework"
author: "johnsp"
# published: 2025-09-30 
Summary: "We're excited to announce the start of the T90 network training series, powered by a completely rewritten JAX-based training script. This launch marks a significant step in our ongoing project to eliminate technical debt, following recent engine upgrades and paving the way for future improvements to our entire data collection and development ecosystem."
draft:true
---

### Announcing the T90 Training Series

- After three years of development on the T80 series, we have officially begun training the new T90 series.
- This run continues the development of the BT4 network, now utilizing a larger network and a Transformer architecture, which we expect to yield significant improvements.
- The primary goal is for the T90 series to become our official networks for competitions like TCEC and CCC, moving away from using side branches with engine-specific improvements.

### A Modern, Rewritten Training Script

- The T90 run is powered by our new training script, a complete rewrite in JAX by `crem`. This is a massive upgrade from the old script, which required an outdated version of Python and TensorFlow from 2021.
  - BT4 was trained on T80 data, and is being used to initialize this training run.
- The rewrite was the main reason for the recent month-long pause in network generation. T80 training had stalled, showing only marginal gains over the last 500 million training games (representing 80,000 iterations of the network).
  - Add image of self learning elo graph, showing the plateau
- Key benefits of the new JAX script:
  - No More Recompiling: The script now runs as a daemon, retraining the model without exiting. This feature alone saves over an hour of model compilation time on each BT4 training cycle.
  - Future-Ready: It provides crucial support for training networks in `fp16`, a key feature for the upcoming v0.33 engine release.
    - Explain how FP16 weights have been popularized by LLMs, along with the Transformer architecture. Explain how FP16 are an improvement over FP32.
  - TODO: Talk with crem for more details about other improvements.

### The Bigger Picture: Eliminating Technical Debt

This launch is a major milestone in our long-term project to modernize our tools and infrastructure.

- Recently Completed (Engine v0.32):
  - A brand new internal API layer was implemented, allowing multiple search algorithms to coexist within the engine.
  - The DAG search algorithm was merged into the master branch. While still in preview, it already shows a +30 Elo gain over the classic search.
  - Policy and Value searches were also added, which are useful for analyzing Maia-style networks and for general debugging.
  - This website has seen many smaller improvements made, including dark mode, multilinugal support and redesigns of the home and downloads pages.
- Future Rewrites Planned:
  - Training Client & Data Servers: We plan to rewrite our Go-based client and servers. The new versions will eliminate several smaller components to make training, benchmarking, and testing much easier, with the goal of replacing our OpenBench instance.
  - Developer Website: A new, centralized developer website will be created to replace the current data collection frontend, our monitoring system, TCEC/CCC notifications, and the Lc0 URL shortener. It may also eventually absorb the functions of our Discord bot, Little Teapot.

---

TODO: Make this more into a story

- Potentially something about Torch joining TCEC Season 29, and how we are bringing the fight to them.
  - Maybe add something about how Stockfish also is having a bit of difficulty making improvements as of late, but hopefully Torch joining will spark some inspiration.
  - Torch is a closed source engine made by Chess.com, with no plans of releasing it, even in binary form commercially, in the future.
- Add a call to action asking for help with future plans
- Mention the issues T90 is having getting off the ground, as it is technically the beta for the new training script. There are many difference and it took time to get the training settings perfect.
