# Initial landscape

Surface scan, 8 October 2026. This is a set of entry points, not a ranking of current SOTA or a recommendation to build any particular system. Abstracts, repository documentation, and product pages were inspected where stated; no full-paper review or reproduction is claimed. Initial notes are AI-assisted and await deeper review.

## PCB design automation

Separate schematic reasoning, placement, routing, and electrical/manufacturing validation. A routing result alone does not establish end-to-end design automation.

- **[PCBWorld](https://arxiv.org/abs/2607.05915v4)** — abstract inspected; September 2026 revision. The authors describe a KiCad-based routing environment supporting reinforcement learning and tool-using LLM agents, with engine-checked evaluation. They report learning-based methods still lagging rule-based routers overall. **Why read:** a concrete way to study methods against existing routing tools. **Unresolved:** benchmark composition, fairness of compute budgets, generalization, and failure cases require full-paper review.
- **[Quilter: how it works](https://docs.quilter.ai/about-quilter/how-does-quilter-work)** — vendor documentation inspected. Describes exploration of layout candidates and stack-ups with physics constraints and Physics Rule Checks. **Why read:** understand the workflow and validation around a commercial system. **Unresolved:** this page does not disclose a reproducible training architecture or establish independent reliability. Do not infer its implementation from unrelated papers.

Review question: where might representation, search, constraint handling, or evaluation offer a useful improvement over strong existing methods?

## Firmware automation

Separate generating code, changing existing firmware, integrating peripherals, and proving behavior on the target hardware.

- **[CraftifAI / FirmGen](https://craftifai.com/products/firmgen)** — discovery lead only. Search results describe an agentic firmware workflow, but the opened page did not expose readable technical content to the research tool. **Next:** inspect documentation or a substantive demonstration. Architecture, supported hardware, reliability, and pricing are unverified; no capability conclusion is drawn here.

Review question: what feedback does a system use beyond compilation, and how does it check timing, peripherals, and behavior? Map established build/test methods alongside newer generation research before judging novelty.

## Mechanical CAD

Separate generating editable geometry, maintaining parametric design intent, and meeting physical/manufacturing requirements.

- **[Text2CAD](https://github.com/SadilKhan/Text2CAD)** — authors' repository inspected; NeurIPS 2024 work. Provides an entry point to text-conditioned sequential parametric CAD generation. **Why read:** inspect the representation and executable research artifacts. **Unresolved:** validity and shape metrics do not by themselves establish that an output meets a real engineering specification. This is a starting reference, not a claim that it remains SOTA.
- **[Autodesk Fusion generative design](https://help.autodesk.com/view/fusion360/ENU/?contextId=GD-OVERVIEW)** — product documentation inspected. Describes generating alternatives under geometric, performance, and manufacturing requirements. **Why read:** distinguish established constrained design exploration from newer text-to-CAD methods. **Unresolved:** which tasks could benefit from an additional method rather than existing functionality?

Review question: where is the difficult part—specifying the design, editing it, searching alternatives, or verifying the result?

## Computer vision in electronics manufacturing

Keep three application groups distinct: defect inspection; assembly/component verification and traceability; and process observation such as counts or cycle times. Their required image detail and ground truth differ. These are review categories, not confirmed company needs.

- **[DeepPCB](https://github.com/tangsanli5201/DeepPCB)** — dataset README inspected. Contains 1,500 aligned template/test image pairs covering six PCB defect classes. The source describes line-scan imaging and artificially added defects. **Why read:** a concrete inspection dataset and evaluation setup. **Limitation:** results on aligned bare-board imagery do not establish assembled-board or CCTV performance. The README also specifies research-only dataset use; commercial reuse needs clarification.
- **[MVTec machine vision technologies](https://www.mvtec.com/knowledge-base/technologies)** and **[Deep Learning Tool](https://www.mvtec.com/products/deep-learning-tool)** — vendor pages inspected. Useful starting points for conventional vision, deep learning, 3D methods, and data preparation. **Limitation:** product descriptions establish the offered workflow, not independent performance on a particular factory line.

Review question: for each application, what must be visible, which methods are appropriate, and what are the costs of cameras, lighting, labels, integration, missed defects, and false alarms?

## What to capture as the review develops

For each worthwhile source, write a short assessment: what it does; how it works; what evidence supports it; where it breaks; and what it suggests checking next. Mark whether only an abstract was inspected, the paper was read, code was examined, or a result was reproduced. Product internals that are undisclosed stay unknown.

Costs have not been researched in this scan. Record published prices or dated quotes where available, and separate licensing, compute, specialist effort, hardware, and integration. Avoid presenting guesses as quotations.
