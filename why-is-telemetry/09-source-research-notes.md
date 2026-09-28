# Source Research Notes

> **Superseded in part (2026-09-24):** the source sweep verified or corrected every source below. See `11-source-sweep.md` for the corrections and `sources/` for the evidence. Notably: workslop is 40% (not 41%); the Paul David counterfactual is group drive; "Path to RSI Agents" is a Preprints.org preprint; replace the archania.org Beer source.

These are source notes for the article and Labs package. Some were identified during this packet build; some were carried forward from the referenced conversation. Open and verify before citing in final prose.

## Historical productivity and general-purpose technologies

### Paul A. David, "The Dynamo and the Computer"

URL identified: https://www.researchgate.net/profile/Paul-David/publication/254399138_The_Dynamo_and_the_Computer_An_Historical_Perspective_on_the_Productivity_Paradox/links/5410ccab0cf2f2b29a411645/The-Dynamo-and-the-Computer-An-Historical-Perspective-on-the-Productivity-Paradox.pdf

Use:

- electrification analogy;
- unit-drive motors;
- productivity paradox;
- old factory layouts limiting new technology.

Drafting note:

Use only as a short historical frame. Avoid a long economic-history detour.

### Brynjolfsson and Hitt, "Beyond Computation"

URL identified: https://www.aeaweb.org/articles?id=10.1257%2Fjep.14.4.23

Use:

- IT value depends on organizational transformation and intangible investments;
- supports the claim that technology alone is not enough.

### Brynjolfsson and Hitt, "Computing Productivity"

URL identified: https://gwern.net/doc/economics/automation/2003-brynjolfsson.pdf

Use:

- firm-level evidence;
- long-period productivity effects;
- complements with work processes and organizational redesign.

### Bresnahan, Brynjolfsson, and Hitt, "Information Technology, Workplace Organization, and the Demand for Skilled Labor"

URL identified: https://cpi.stanford.edu/_media/pdf/Reference%20Media/Bresnahan_Brynjolfsson_Hitt_2002_Organizations.pdf

Use:

- complementarities among IT, workplace reorganization, and new products/services.

### Brynjolfsson, Rock, and Syverson, "Artificial Intelligence and the Modern Productivity Paradox"

URL identified: https://www.nber.org/papers/w24001

Use:

- AI as a general-purpose technology;
- full effects require complementary innovations.

### Brynjolfsson, Rock, and Syverson, "The Productivity J-Curve"

URLs identified:

- https://swlb2.aeaweb.org/articles?id=10.1257%2Fmac.20180386
- https://ide.mit.edu/sites/default/files/publications/jcurve.pdf

Use:

- intangible complementary investments;
- J-curve framing;
- AI explicitly included as a GPT.

## Workslop and AI productivity

### BetterUp Labs / Stanford Social Media Lab, workslop

URLs identified:

- https://www.betterup.com/blog/hidden-costs-workslop
- https://www.betterup.com/hubfs/Post-Uplift%20content/BetterUp_Uplift_The%20hidden%20cost%20of%20workslop.pdf

Use:

- definition of workslop;
- 41 percent encountered it;
- nearly two hours of rework per instance.

Verification:

Open the PDF before using exact figures.

### Holweg and Davenport, "Don't Let AI Slop Muck Up Your Company's Processes"

URL identified: https://hbr.org/2026/06/dont-let-ai-slop-muck-up-your-companys-processes

Use:

- organization-level knowledge decay;
- AI slop as process and knowledge infrastructure risk.

Note:

HBR may be paywalled. Use sparingly or cite if accessible.

### ILO, "The impact of GenAI on jobs, productivity and work organization"

URL identified: https://www.ilo.org/publications/impact-genai-jobs-productivity-and-work-organization-review-empirical

Use:

- empirical evidence is mixed;
- reported time savings have not necessarily translated into measured output, earnings, or employment.

### ILO, "The Aggregation Paradox of AI"

URL identified: https://www.ilo.org/publications/aggregation-paradox-ai-why-do-micro-economic-productivity-gains-ai

Use:

- individual productivity gains may not scale cleanly to firm or macro productivity;
- useful for Labs if the article needs a stronger macro anchor.

## Self-improving agents and recursive improvement

### "Self-Improvements in Modern Agentic Systems: A Survey"

URLs identified:

- https://arxiv.org/abs/2607.13104
- https://selfimproving-agent.github.io/

Use:

- modern agents can improve model weights or scaffolds;
- scaffolds include prompts, memory, tools, and control logic;
- good Labs anchor for why workflow, memory, and tool updates matter.

### FlowEvo

URL identified: https://arxiv.org/abs/2607.21596

Use:

- workflow-to-skill compilation;
- skill-to-workflow feedback;
- skill curation to suppress negative transfer.

### "The Path to Recursive Self-Improving Agents"

URL identified: https://self-improving-agent.com/

Use:

- five-level grading idea;
- mutable state includes model, harness, data system, trainer, and improvement mechanism.

Note:

Use mainly for Labs. Circle News probably does not need this unless the close names RSI.

## Control-loop and organizational prior art

### IBM / MAPE-K

URL identified: https://www.redbooks.ibm.com/redbooks/pdfs/sg246665.pdf

Use:

- Monitor, Analyze, Plan, Execute over Knowledge;
- control-loop precedent for adaptive systems.

### Google SRE book

URLs identified:

- https://sre.google/sre-book/table-of-contents/
- https://sre.google/sre-book/embracing-risk/

Use:

- error budgets;
- deliberate risk;
- reliability as managed tradeoff.

### High Reliability Organizations

URL identified: https://www.high-reliability.org/Weick-Sutcliffe

Use:

- preoccupation with failure;
- reluctance to simplify;
- sensitivity to operations;
- commitment to resilience;
- deference to expertise.

### Stafford Beer and Viable System Model

URL identified: https://archania.org/p/individuals/scientists/systems-scientists/stafford-beer

Use:

- recursive governance;
- operations, coordination, control, intelligence, policy.

## Source plan for Circle News

Keep inline citations few:

1. One historical productivity source.
2. One organizational complement / J-curve source.
3. One workslop source.
4. One source on mixed productivity translation or organizational AI slop.
5. Optional self-improving-agent source only if the close needs it.

## Verification queue

Before drafting:

1. Open BetterUp PDF and confirm exact figures.
2. Open Paul David source and confirm the unit-drive/factory redesign language.
3. Open J-curve source and confirm AI/complementary-investment language.
4. Open ILO brief and confirm productivity wording.
5. Decide whether HBR is accessible enough to cite in the public column.
6. If citing agent RSI work, prefer arXiv over commentary.
