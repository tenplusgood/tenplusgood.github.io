---
layout: project-page
permalink: /a-harness-page/
title: "Affordance Agent Harness: Verification-Gated Skill Orchestration"
---

<!-- 标题与作者 -->
<h1 class="title is-1">Affordance Agent Harness: Verification-Gated Skill Orchestration</h1>

<div class="authors">
  <a href="http://www.wonghougin.me/">Haojian Huang</a><sup>1,2*</sup>, 
  <a href="https://tenplusgood.github.io/"><strong>Jiahao Shi</strong></a><sup>2,3*</sup>, 
  Yinchuan Li<sup>1,2</sup>, 
  Yingcong Chen<sup>1,2†</sup>
</div>

<div class="affiliations">
  <sup>1</sup>HKUST(GZ), <sup>2</sup>Knowin, <sup>3</sup>Harbin Engineering University<br>
  <sup>*</sup>Equal Contribution, <sup>†</sup>Corresponding Author
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
    Affordance grounding requires identifying <em>where</em> and <em>how</em> an agent should interact in open-world scenes, where actionable regions are often small, occluded, reflective, and visually ambiguous. Recent systems therefore combine multiple skills (e.g., detection, segmentation, interaction-imagination), yet most orchestrate them with fixed pipelines that are poorly matched to per-instance difficulty, offer limited targeted recovery from intermediate errors, and fail to amortize experience over recurring objects. We observe that many failures stem not from the lack of stronger models but from the lack of a system-level ability to actively acquire and <strong>validate</strong> evidence under bounded inference cost, where "verification" must rely on relative signals rather than ground-truth labels at test time. To this end, we propose <strong>Affordance Agent Harness</strong>, a closed-loop runtime that unifies heterogeneous skills with an evidence store and cost control, retrieves episodic memories to provide priors for recurring categories, and employs a Router to adaptively select and parameterize skills. Crucially, an affordance-specific Verifier <strong>gates commitments</strong> using self-consistency, cross-scale stability, and evidence sufficiency, triggering targeted retries when needed before a final judge fuses accumulated evidence and trajectories into the prediction. Experiments on multiple affordance benchmarks and difficulty-controlled subsets demonstrate a superior accuracy–cost Pareto frontier over fixed-pipeline baselines, improving grounding quality while reducing average skill calls and latency.
  </p>
</div>

<!-- Motivation 核心动力 -->
<h2 class="section-title">Motivation</h2>
<p style="line-height: 1.8; margin-bottom: 2rem; text-align: justify;">
  Affordance grounding remains brittle when decisions must be geometry-aware and evidence must be aggregated coherently across heterogeneous cues and tools. Existing agent systems exhibit three limitations: (1) <strong>Fixed Execution</strong>: they execute skills in a predetermined order regardless of input complexity; (2) <strong>Lack of Closed-loop Correction</strong>: they lack a mechanism to diagnose failure sources and re-invoke responsible skills when intermediate outputs conflict; (3) <strong>No Persistent Experience</strong>: recurring objects are re-solved from scratch each time. 
</p>
<p style="line-height: 1.8; margin-bottom: 2rem; text-align: justify;">
  We reframes affordance grounding as a budgeted, evidence-seeking decision process, where tool usage is a per-instance policy rather than a static script. We rely on three families of relative signals: (i) <strong>cross-tool consistency</strong>, (ii) <strong>cross-scale stability</strong>, and (iii) <strong>evidence sufficiency</strong>.
</p>

<!-- Methodology 核心方法 -->
<h2 class="section-title">Methodology</h2>
<div style="text-align: center; margin-bottom: 2rem;">
  <img src="{{ '/images/flowchat_new.png' | relative_url }}" style="width: 100%; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.1);">
</div>
<p style="line-height: 1.8; margin-bottom: 2rem; text-align: justify;">
  A-Harness consists of four key components:
</p>
<ul style="line-height: 1.8; margin-bottom: 3rem; text-align: justify;">
  <li><strong>Evidence Store with Provenance</strong>: Accumulates heterogeneous skill outputs (boxes, masks, text) tagged with their source and zoom level to enable cross-skill agreement checks.</li>
  <li><strong>Two-Tier Memory</strong>: A <em>Common-sense Bank</em> for stable priors of frequent objects and a <em>Test-time Episodic Bank</em> that accumulates verifier-accepted successful trajectories for online adaptation.</li>
  <li><strong>Budget-Aware Router</strong>: Selects the next skill and its parameters by choosing the action most likely to resolve current uncertainty per unit cost (benefit-cost ratio).</li>
  <li><strong>Verifier</strong>: Sidesteps the absence of ground truth by using relative diagnostics (consistency, stability, sufficiency) to gate commitments and trigger <strong>targeted retries</strong>.</li>
</ul>

<!-- Results 实验结果 -->
<h2 class="section-title">Quantitative Results</h2>
<div style="overflow-x: auto; white-space: nowrap; padding-bottom: 1rem; margin-bottom: 3rem;">
  
  <!-- Table 1: ReasonAff & UMD -->
  <div style="display: inline-block; vertical-align: top; margin-right: 2rem; background: #fff; border: 1px solid #eee; border-radius: 8px; padding: 1rem; box-shadow: 0 2px 10px rgba(0,0,0,0.05);">
    <h3 style="font-size: 1.1rem; margin-top: 0; text-align: center;">Results on ReasonAff & UMD</h3>
    <table style="border-collapse: collapse; text-align: center; font-size: 0.85rem;">
      <thead>
        <tr style="border-bottom: 2px solid #333;">
          <th style="padding: 8px; text-align: left;">Model</th>
          <th style="padding: 8px;">ReasonAff (gIoU)</th>
          <th style="padding: 8px;">ReasonAff (cIoU)</th>
          <th style="padding: 8px;">UMD (gIoU)</th>
          <th style="padding: 8px;">UMD (cIoU)</th>
        </tr>
      </thead>
      <tbody>
        <tr style="border-bottom: 1px solid #eee;">
          <td style="padding: 8px; text-align: left;">LISA-7B</td>
          <td style="padding: 8px;">38.17</td>
          <td style="padding: 8px;">40.58</td>
          <td style="padding: 8px;">41.90</td>
          <td style="padding: 8px;">41.23</td>
        </tr>
        <tr style="border-bottom: 1px solid #eee;">
          <td style="padding: 8px; text-align: left;">AffordanceLLM</td>
          <td style="padding: 8px;">48.49</td>
          <td style="padding: 8px;">38.61</td>
          <td style="padding: 8px;">43.11</td>
          <td style="padding: 8px;">38.97</td>
        </tr>
        <tr style="border-bottom: 1px solid #eee; background-color: #fff9f9;">
          <td style="padding: 8px; text-align: left;">Affordance-R1</td>
          <td style="padding: 8px;">67.41</td>
          <td style="padding: 8px;">62.72</td>
          <td style="padding: 8px;">49.85</td>
          <td style="padding: 8px;">42.24</td>
        </tr>
        <tr style="background-color: #f0f7ff; font-weight: bold;">
          <td style="padding: 8px; text-align: left;">A-Harness (Claude-Opus)</td>
          <td style="padding: 8px;">69.68</td>
          <td style="padding: 8px;">70.88</td>
          <td style="padding: 8px;">54.94</td>
          <td style="padding: 8px;">55.04</td>
        </tr>
      </tbody>
    </table>
  </div>

  <!-- Table 2: RAGNet (3DOI & HANDAL) -->
  <div style="display: inline-block; vertical-align: top; background: #fff; border: 1px solid #eee; border-radius: 8px; padding: 1rem; box-shadow: 0 2px 10px rgba(0,0,0,0.05);">
    <h3 style="font-size: 1.1rem; margin-top: 0; text-align: center;">Results on RAGNet (3DOI & HANDAL)</h3>
    <table style="border-collapse: collapse; text-align: center; font-size: 0.85rem;">
      <thead>
        <tr style="border-bottom: 2px solid #333;">
          <th style="padding: 8px; text-align: left;">Method</th>
          <th style="padding: 8px;">3DOI (gIoU)</th>
          <th style="padding: 8px;">3DOI (cIoU)</th>
          <th style="padding: 8px;">HANDAL-E (gIoU)</th>
          <th style="padding: 8px;">HANDAL-H (gIoU)</th>
        </tr>
      </thead>
      <tbody>
        <tr style="border-bottom: 1px solid #eee;">
          <td style="padding: 8px; text-align: left;">Vision-Reasoner</td>
          <td style="padding: 8px;">39.6</td>
          <td style="padding: 8px;">30.3</td>
          <td style="padding: 8px;">29.6</td>
          <td style="padding: 8px;">27.7</td>
        </tr>
        <tr style="border-bottom: 1px solid #eee;">
          <td style="padding: 8px; text-align: left;">Affordance-R1</td>
          <td style="padding: 8px;">39.0</td>
          <td style="padding: 8px;">33.4</td>
          <td style="padding: 8px;">43.1</td>
          <td style="padding: 8px;">40.7</td>
        </tr>
        <tr style="border-bottom: 1px solid #eee;">
          <td style="padding: 8px; text-align: left;">AffordanceVLM</td>
          <td style="padding: 8px;">38.1</td>
          <td style="padding: 8px;">39.4</td>
          <td style="padding: 8px;">58.3</td>
          <td style="padding: 8px;">58.2</td>
        </tr>
        <tr style="background-color: #f0f7ff; font-weight: bold;">
          <td style="padding: 8px; text-align: left;">A-Harness (Full)</td>
          <td style="padding: 8px;">65.6</td>
          <td style="padding: 8px;">53.7</td>
          <td style="padding: 8px;">63.5</td>
          <td style="padding: 8px;">62.8</td>
        </tr>
      </tbody>
    </table>
  </div>

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
