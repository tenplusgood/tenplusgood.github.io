---
layout: project-page
permalink: /a-harness-page/
title: "Affordance Agent Harness: Verification-Gated Skill Orchestration"
---

<!-- 标题与作者 -->
<h1 class="title is-1">Affordance Agent Harness: Verification-Gated Skill Orchestration</h1>

<div class="authors">
  <a href="http://www.wonghougin.me/">Haojian Huang</a><sup>1,2</sup>, 
  <a href="https://tenplusgood.github.io/"><strong>Jiahao Shi</strong></a><sup>2,3</sup>, 
  Yinchuan Li<sup>1,2</sup>, 
  Yingcong Chen<sup>1,2†</sup>
</div>

<div class="affiliations">
  <sup>1</sup>HKUST(GZ), <sup>2</sup>Knowin, <sup>3</sup>Harbin Engineering University<br>
  <sup>†</sup>Corresponding Author
</div>

<!-- 链接按钮组 -->
<div class="link-buttons">
  <a href="https://arxiv.org/abs/2511.21021" class="btn"><i class="fas fa-file-pdf"></i> Paper (arXiv)</a>
  <a href="#" class="btn"><i class="fab fa-github"></i> Code (Coming Soon)</a>
  <a href="#" class="btn"><i class="fas fa-video"></i> Video</a>
  <a href="#" class="btn"><i class="fas fa-database"></i> Dataset</a>
</div>

<!-- Teaser 展示图 -->
<div class="teaser-box">
  <img src="{{ '/images/comp.png' | relative_url }}" alt="A-Harness Teaser">
  <p style="margin-top: 1rem; font-style: italic;">A-Harness: A verification-gated runtime that unifies heterogeneous skills with adaptive routing and episodic memory.</p>
</div>

<!-- Abstract 摘要卡片 -->
<div class="abstract-box">
  <h2>Abstract</h2>
  <p>
    Affordance grounding requires identifying <em>where</em> and <em>how</em> an agent should interact in open-world scenes. Recent systems combine multiple skills (e.g., detection, segmentation), yet most orchestrate them with fixed pipelines that fail to recover from intermediate errors. We propose <strong>Affordance Agent Harness</strong>, a closed-loop runtime that unifies heterogeneous skills with an evidence store and cost control. Crucially, an affordance-specific <strong>Verifier</strong> gates commitments using self-consistency, cross-scale stability, and evidence sufficiency, triggering targeted retries when needed. Experiments demonstrate a superior accuracy-cost Pareto frontier over fixed-pipeline baselines, improving grounding quality while reducing average skill calls.
  </p>
</div>

<!-- Motivation 核心动力 -->
<h2 class="section-title">Motivation</h2>
<p style="line-height: 1.8; margin-bottom: 2rem; text-align: justify;">
  Many affordance grounding failures stem not from the lack of stronger models, but from the lack of a system-level ability to <strong>actively acquire and validate evidence</strong> under bounded cost. Without test-time labels, we operationalize relative diagnostics: (1) <strong>Cross-tool consistency</strong>, (2) <strong>Cross-scale stability</strong>, and (3) <strong>Evidence sufficiency</strong>. This reframes grounding as a budgeted, evidence-seeking decision process.
</p>

<!-- Methodology 核心方法 -->
<h2 class="section-title">Methodology</h2>
<div style="text-align: center; margin-bottom: 2rem;">
  <img src="{{ '/images/flowchat_new.png' | relative_url }}" style="width: 100%; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.1);">
</div>
<p style="line-height: 1.8; margin-bottom: 3rem; text-align: justify;">
  A-Harness consists of four key components: (i) an <strong>Evidence Store</strong> that accumulates heterogeneous skill outputs with provenance, (ii) a <strong>Two-Tier Memory</strong> (Common-sense Bank and Test-time Episodic Bank) for reusable priors, (iii) a <strong>Router</strong> for budget-aware skill selection, and (iv) a <strong>Verifier</strong> for gating commitment and triggering targeted retries.
</p>

<!-- Results 实验结果 -->
<h2 class="section-title">Quantitative Results</h2>
<div style="overflow-x: auto; margin-bottom: 3rem;">
  <table style="width: 100%; border-collapse: collapse; text-align: center; font-size: 0.9rem;">
    <thead>
      <tr style="border-bottom: 2px solid #333;">
        <th style="padding: 10px;">Model</th>
        <th style="padding: 10px;">ReasonAff (gIoU)</th>
        <th style="padding: 10px;">ReasonAff (cIoU)</th>
        <th style="padding: 10px;">UMD (gIoU)</th>
        <th style="padding: 10px;">UMD (cIoU)</th>
      </tr>
    </thead>
    <tbody>
      <tr style="border-bottom: 1px solid #eee;">
        <td style="padding: 10px; text-align: left;">AffordanceLLM</td>
        <td style="padding: 10px;">48.49</td>
        <td style="padding: 10px;">38.61</td>
        <td style="padding: 10px;">43.11</td>
        <td style="padding: 10px;">38.97</td>
      </tr>
      <tr style="border-bottom: 1px solid #eee;">
        <td style="padding: 10px; text-align: left;">Affordance-R1</td>
        <td style="padding: 10px;">67.41</td>
        <td style="padding: 10px;">62.72</td>
        <td style="padding: 10px;">49.85</td>
        <td style="padding: 10px;">42.24</td>
      </tr>
      <tr style="background-color: #f9f9f9; font-weight: bold;">
        <td style="padding: 10px; text-align: left;">A-Harness (Claude-Opus)</td>
        <td style="padding: 10px;">69.68</td>
        <td style="padding: 10px;">70.88</td>
        <td style="padding: 10px;">54.94</td>
        <td style="padding: 10px;">55.04</td>
      </tr>
    </tbody>
  </table>
</div>

<!-- BibTeX 引用 -->
<h2 class="section-title">BibTeX</h2>
<div class="bibtex-box">
@article{huang2026aharness,
  title={Affordance Agent Harness: Verification-Gated Skill Orchestration},
  author={Huang, Haojian and Shi, Jiahao and Li, Yinchuan and Chen, Yingcong},
  journal={Submitted to ECCV},
  year={2026}
}
</div>
