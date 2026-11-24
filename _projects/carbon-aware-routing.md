---
layout: page
title: Carbon-Aware Routing for Multilingual LLMs
description: does routing on real grid carbon change which models answer, and does knowing the language help? — Harvard CS 2880 final project
img: assets/img/projects/carbon-aware-routing.png
importance: 3
category: research
---

_Carbon-aware routing for multilingual LLMs_ is my final project for Harvard CS 2880, presented in November 2026 and made with Louis Liu.

GreenServ, an existing LLM router, decides which model answers each query based on energy use. But a deployed router has a location, and two things that come with it are left out: how dirty the local power grid is, and what language the query is in. We asked two questions:

- **Q1, the local grid.** If the router pays for carbon at the local grid instead of energy, do its choices change, and is it more accurate at equal carbon?
- **Q2, the local language.** If the router also knows the query's language, is it more accurate at equal carbon, especially for low-resource languages?

## Approach

Six open models, from 2B to 31B parameters, answered every question once on an A100. We stored each answer's accuracy and GPU energy. The questions came from XNLI, Belebele, and MGSM in 8 languages, plus a low-resource set of Belebele in 12 more languages. A LinUCB bandit router then replayed those stored answers across six grid zones, using 2025 hourly carbon intensity data, and traded off accuracy against carbon cost.

## Findings

- **Adding the grid gets the same accuracy for less carbon.** The router used 12–14% less carbon than GreenServ at the same or slightly better accuracy (0.836 vs 0.828 on the main set), and the weakest language was no worse off.
- **But answer quality follows clean grids.** Clean grids like Sweden and France gain 2–5 accuracy points for a few grams of CO₂. Poland saves 44% of its carbon but loses 8 points, so users on dirty grids get worse answers. Earlier carbon-aware routing work doesn't report results by grid or language, so this equity cost goes unnoticed.
- **Knowing the language barely helps.** Every language ranks the six models in nearly the same order (rank correlation 0.94), so language tells the router how hard a question is, not which model to use.

<a href="{{ '/assets/pdf/cs2880-final-presentation.pdf' | relative_url }}" target="_blank" rel="noopener">Open the full slide deck (PDF) ↗</a>

<div style="position: relative; width: 100%; aspect-ratio: 16 / 9; margin: 1.5rem 0;">
  <iframe
    src="{{ '/assets/pdf/cs2880-final-presentation.pdf' | relative_url }}"
    title="Carbon-aware routing for multilingual LLMs: slide deck"
    loading="lazy"
    style="position: absolute; inset: 0; width: 100%; height: 100%; border: 1px solid var(--global-divider-color, #e8e8e8); border-radius: 6px;"
  ></iframe>
</div>
