---
layout: project-page
permalink: /a-harness-page/
title: "Affordance Agent Harness: Verification-Gated Skill Orchestration"
---

<!-- 标题与作者 -->
<h1 class="title is-1">Affordance Agent Harness: Verification-Gated Skill Orchestration</h1>

<div class="authors">
  <a href="https://jethrojames.github.io/">Haojian Huang</a><sup>1,2*</sup>, 
  <a href="https://tenplusgood.github.io/">Jiahao Shi</a><sup>2,3*</sup>, 
  <a href="https://yinchuanll.github.io/">Yinchuan Li</a><sup>1,2</sup>, 
  <a href="https://www.yingcong.me/">Yingcong Chen</a><sup>1,2†</sup>
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
  <embed src="{{ '/images/skills.pdf' | relative_url }}" type="application/pdf" width="100%" height="600px" style="border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.1);">
  <p style="margin-top: 1rem; font-size: 0.9rem; color: #666;">
    If the PDF is not displaying, you can <a href="{{ '/images/skills.pdf' | relative_url }}" target="_blank">click here to view it in a new tab</a>.
  </p>
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
      <h3 style="font-size: 1.1rem; margin-top: 0; text-align: center;">Quantitative results on ReasonAff and UMD datasets</h3>
      <table style="border-collapse: collapse; text-align: center; font-size: 0.8rem;">
        <thead>
          <tr style="border-bottom: 2px solid #333;">
            <th rowspan="2" style="padding: 6px; text-align: left; border-right: 1px solid #eee;">Model</th>
            <th colspan="4" style="padding: 6px; border-right: 1px solid #eee;">ReasonAff</th>
            <th colspan="4" style="padding: 6px;">UMD</th>
          </tr>
          <tr style="border-bottom: 2px solid #333;">
            <th style="padding: 6px;">gIoU</th>
            <th style="padding: 6px;">cIoU</th>
            <th style="padding: 6px;">$P_{50}$</th>
            <th style="padding: 6px; border-right: 1px solid #eee;">$P_{50-95}$</th>
            <th style="padding: 6px;">gIoU</th>
            <th style="padding: 6px;">cIoU</th>
            <th style="padding: 6px;">$P_{50}$</th>
            <th style="padding: 6px;">$P_{50-95}$</th>
          </tr>
        </thead>
        <tbody>
          <tr style="border-bottom: 1px solid #eee; color: #888;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">VLPart</td>
            <td style="padding: 6px;">4.21</td>
            <td style="padding: 6px;">3.88</td>
            <td style="padding: 6px;">1.31</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">0.85</td>
            <td style="padding: 6px;">--</td>
            <td style="padding: 6px;">--</td>
            <td style="padding: 6px;">--</td>
            <td style="padding: 6px;">--</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee; color: #888;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">OVSeg</td>
            <td style="padding: 6px;">16.52</td>
            <td style="padding: 6px;">10.59</td>
            <td style="padding: 6px;">9.89</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">4.12</td>
            <td style="padding: 6px;">--</td>
            <td style="padding: 6px;">--</td>
            <td style="padding: 6px;">--</td>
            <td style="padding: 6px;">--</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee; color: #888;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">SAN</td>
            <td style="padding: 6px;">10.21</td>
            <td style="padding: 6px;">13.45</td>
            <td style="padding: 6px;">7.18</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">3.17</td>
            <td style="padding: 6px;">--</td>
            <td style="padding: 6px;">--</td>
            <td style="padding: 6px;">--</td>
            <td style="padding: 6px;">--</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">LISA-7B</td>
            <td style="padding: 6px;">38.17</td>
            <td style="padding: 6px;">40.58</td>
            <td style="padding: 6px;">33.62</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">19.69</td>
            <td style="padding: 6px;">41.90</td>
            <td style="padding: 6px;">41.23</td>
            <td style="padding: 6px;">39.65</td>
            <td style="padding: 6px;">19.33</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">SAM4MLLM</td>
            <td style="padding: 6px;">45.51</td>
            <td style="padding: 6px;">33.64</td>
            <td style="padding: 6px;">43.48</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">22.79</td>
            <td style="padding: 6px;">12.40</td>
            <td style="padding: 6px;">8.41</td>
            <td style="padding: 6px;">4.12</td>
            <td style="padding: 6px;">0.05</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">AffordanceLLM</td>
            <td style="padding: 6px;">48.49</td>
            <td style="padding: 6px;">38.61</td>
            <td style="padding: 6px;">42.11</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">20.19</td>
            <td style="padding: 6px;">43.11</td>
            <td style="padding: 6px;">38.97</td>
            <td style="padding: 6px;">41.56</td>
            <td style="padding: 6px;">22.36</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">InternVL3-8B</td>
            <td style="padding: 6px;">31.79</td>
            <td style="padding: 6px;">24.68</td>
            <td style="padding: 6px;">35.41</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">21.93</td>
            <td style="padding: 6px;">--</td>
            <td style="padding: 6px;">--</td>
            <td style="padding: 6px;">--</td>
            <td style="padding: 6px;">--</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">InternVL3-7B</td>
            <td style="padding: 6px;">--</td>
            <td style="padding: 6px;">--</td>
            <td style="padding: 6px;">--</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">--</td>
            <td style="padding: 6px;">30.46</td>
            <td style="padding: 6px;">28.73</td>
            <td style="padding: 6px;">18.67</td>
            <td style="padding: 6px;">9.94</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">Qwen2.5VL-7B</td>
            <td style="padding: 6px;">25.18</td>
            <td style="padding: 6px;">20.54</td>
            <td style="padding: 6px;">26.00</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">15.82</td>
            <td style="padding: 6px;">33.21</td>
            <td style="padding: 6px;">29.83</td>
            <td style="padding: 6px;">25.17</td>
            <td style="padding: 6px;">10.45</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">AffordanceVLM</td>
            <td style="padding: 6px;">30.50</td>
            <td style="padding: 6px;">25.54</td>
            <td style="padding: 6px;">30.29</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">18.31</td>
            <td style="padding: 6px;">25.41</td>
            <td style="padding: 6px;">17.96</td>
            <td style="padding: 6px;">9.37</td>
            <td style="padding: 6px;">25.10</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">Seg-Zero</td>
            <td style="padding: 6px;">59.26</td>
            <td style="padding: 6px;">48.03</td>
            <td style="padding: 6px;">61.33</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">45.87</td>
            <td style="padding: 6px;">44.26</td>
            <td style="padding: 6px;">39.30</td>
            <td style="padding: 6px;">39.93</td>
            <td style="padding: 6px;">16.53</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">Vision Reasoner</td>
            <td style="padding: 6px;">63.04</td>
            <td style="padding: 6px;">52.70</td>
            <td style="padding: 6px;">67.33</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">47.23</td>
            <td style="padding: 6px;">44.00</td>
            <td style="padding: 6px;">39.71</td>
            <td style="padding: 6px;">39.04</td>
            <td style="padding: 6px;">16.10</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">Affordance-R1</td>
            <td style="padding: 6px;">67.41</td>
            <td style="padding: 6px;">62.72</td>
            <td style="padding: 6px;">74.50</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">55.22</td>
            <td style="padding: 6px;">49.85</td>
            <td style="padding: 6px;">42.24</td>
            <td style="padding: 6px;">53.35</td>
            <td style="padding: 6px;">34.08</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">ConverSeg</td>
            <td style="padding: 6px;">30.11</td>
            <td style="padding: 6px;">25.08</td>
            <td style="padding: 6px;">30.50</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">17.02</td>
            <td style="padding: 6px;">33.27</td>
            <td style="padding: 6px;">10.37</td>
            <td style="padding: 6px;">32.63</td>
            <td style="padding: 6px;">13.59</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee; background-color: #fafafa;">
            <td colspan="9" style="padding: 6px; text-align: left; font-style: italic;">w/o A-Harness</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">Only w/ Det. & Seg. skills</td>
            <td style="padding: 6px;">51.86</td>
            <td style="padding: 6px;">43.73</td>
            <td style="padding: 6px;">57.00</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">38.30</td>
            <td style="padding: 6px;">46.53</td>
            <td style="padding: 6px;">37.77</td>
            <td style="padding: 6px;">53.24</td>
            <td style="padding: 6px;">30.56</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">Full Fixed Skill Chain</td>
            <td style="padding: 6px;">55.05</td>
            <td style="padding: 6px;">49.57</td>
            <td style="padding: 6px;">58.07</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">37.48</td>
            <td style="padding: 6px;">50.19</td>
            <td style="padding: 6px;">49.24</td>
            <td style="padding: 6px;">55.88</td>
            <td style="padding: 6px;">29.75</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee; background-color: #fafafa;">
            <td colspan="9" style="padding: 6px; text-align: left; font-style: italic;">w/ A-Harness (Ours)</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">w/ Qwen-3.5-397B-A17B</td>
            <td style="padding: 6px;">58.51</td>
            <td style="padding: 6px;">49.47</td>
            <td style="padding: 6px;">64.83</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">44.73</td>
            <td style="padding: 6px; font-weight: bold;">57.61</td>
            <td style="padding: 6px;">53.39</td>
            <td style="padding: 6px; font-weight: bold;">67.71</td>
            <td style="padding: 6px; font-weight: bold;">37.44</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">w/ Gemini-3-flash</td>
            <td style="padding: 6px;">58.27</td>
            <td style="padding: 6px;">47.25</td>
            <td style="padding: 6px;">63.68</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">45.91</td>
            <td style="padding: 6px;">51.33</td>
            <td style="padding: 6px;">46.49</td>
            <td style="padding: 6px;">53.60</td>
            <td style="padding: 6px;">28.17</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">w/ GPT-4o</td>
            <td style="padding: 6px;">60.53</td>
            <td style="padding: 6px;">54.91</td>
            <td style="padding: 6px;">66.73</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">45.53</td>
            <td style="padding: 6px;">52.74</td>
            <td style="padding: 6px;">50.04</td>
            <td style="padding: 6px;">57.62</td>
            <td style="padding: 6px;">29.85</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">w/ GLM-5</td>
            <td style="padding: 6px;">60.72</td>
            <td style="padding: 6px;">55.02</td>
            <td style="padding: 6px;">66.78</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">45.44</td>
            <td style="padding: 6px;">54.28</td>
            <td style="padding: 6px;">54.06</td>
            <td style="padding: 6px;">61.76</td>
            <td style="padding: 6px;">33.94</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">w/ Claude-Sonnet-4.6</td>
            <td style="padding: 6px;">66.48</td>
            <td style="padding: 6px;">62.82</td>
            <td style="padding: 6px;">73.19</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">53.38</td>
            <td style="padding: 6px;">53.72</td>
            <td style="padding: 6px;">51.15</td>
            <td style="padding: 6px;">62.50</td>
            <td style="padding: 6px;">33.31</td>
          </tr>
          <tr style="background-color: #f0f7ff; font-weight: bold;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">w/ Claude-Opus-4.6</td>
            <td style="padding: 6px;">69.68</td>
            <td style="padding: 6px;">70.88</td>
            <td style="padding: 6px;">77.50</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">56.35</td>
            <td style="padding: 6px;">54.94</td>
            <td style="padding: 6px;">55.04</td>
            <td style="padding: 6px;">64.67</td>
            <td style="padding: 6px;">36.80</td>
          </tr>
        </tbody>
      </table>
    </div>
  
    <!-- Table 2: RAGNet (3DOI & HANDAL) -->
    <div style="display: inline-block; vertical-align: top; background: #fff; border: 1px solid #eee; border-radius: 8px; padding: 1rem; box-shadow: 0 2px 10px rgba(0,0,0,0.05);">
      <h3 style="font-size: 1.1rem; margin-top: 0; text-align: center;">Zero-shot comparison with baselines and ablation on $\mathcal{M}^\text{CS}$</h3>
      <table style="border-collapse: collapse; text-align: center; font-size: 0.8rem;">
        <thead>
          <tr style="border-bottom: 2px solid #333;">
            <th rowspan="2" style="padding: 6px; text-align: left; border-right: 1px solid #eee;">Method / Setting</th>
            <th colspan="2" style="padding: 6px; border-right: 1px solid #eee;">3DOI</th>
            <th colspan="2" style="padding: 6px; border-right: 1px solid #eee;">HANDAL-easy</th>
            <th colspan="2" style="padding: 6px;">HANDAL-hard</th>
          </tr>
          <tr style="border-bottom: 2px solid #333;">
            <th style="padding: 6px;">gIoU</th>
            <th style="padding: 6px; border-right: 1px solid #eee;">cIoU</th>
            <th style="padding: 6px;">gIoU</th>
            <th style="padding: 6px; border-right: 1px solid #eee;">cIoU</th>
            <th style="padding: 6px;">gIoU</th>
            <th style="padding: 6px;">cIoU</th>
          </tr>
        </thead>
        <tbody>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">G-DINO</td>
            <td style="padding: 6px;">4.1</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">3.9</td>
            <td style="padding: 6px;">3.6</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">3.0</td>
            <td style="padding: 6px;">3.4</td>
            <td style="padding: 6px;">3.1</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">LISA</td>
            <td style="padding: 6px;">12.3</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">8.1</td>
            <td style="padding: 6px;">15.5</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">11.9</td>
            <td style="padding: 6px;">12.3</td>
            <td style="padding: 6px;">8.1</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">GLaMM</td>
            <td style="padding: 6px;">4.4</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">2.9</td>
            <td style="padding: 6px;">4.7</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">3.5</td>
            <td style="padding: 6px;">5.0</td>
            <td style="padding: 6px;">3.5</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">Vision-Reasoner</td>
            <td style="padding: 6px;">39.6</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">30.3</td>
            <td style="padding: 6px;">29.6</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">19.8</td>
            <td style="padding: 6px;">27.7</td>
            <td style="padding: 6px;">16.7</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">Affordance-R1</td>
            <td style="padding: 6px;">39.0</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">33.4</td>
            <td style="padding: 6px;">43.1</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">38.7</td>
            <td style="padding: 6px;">40.7</td>
            <td style="padding: 6px;">37.9</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">AffordanceVLM</td>
            <td style="padding: 6px;">38.1</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">39.4</td>
            <td style="padding: 6px;">58.3</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">58.1</td>
            <td style="padding: 6px;">58.2</td>
            <td style="padding: 6px;">57.8</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee; background-color: #fafafa;">
            <td style="padding: 6px; text-align: left; font-style: italic; border-right: 1px solid #eee;">A-Harness (w/o $\mathcal{M}^{\text{CS}}$)</td>
            <td style="padding: 6px;">56.5</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">47.2</td>
            <td style="padding: 6px;">58.4</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">57.6</td>
            <td style="padding: 6px;">55.3</td>
            <td style="padding: 6px;">55.1</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">w/ $\mathcal{M}^\text{CS}$-a</td>
            <td style="padding: 6px;">57.9</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">50.9</td>
            <td style="padding: 6px;">62.4</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">62.1</td>
            <td style="padding: 6px;">49.8</td>
            <td style="padding: 6px;">47.4</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">w/ $\mathcal{M}^\text{CS}$-b</td>
            <td style="padding: 6px;">63.8</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">52.0</td>
            <td style="padding: 6px;">61.4</td>
            <td style="padding: 6px; border-right: 1px solid #eee; font-weight: bold;">63.3</td>
            <td style="padding: 6px;">60.6</td>
            <td style="padding: 6px;">61.0</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">w/ $\mathcal{M}^\text{CS}$-c</td>
            <td style="padding: 6px;">59.3</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">45.4</td>
            <td style="padding: 6px;">62.7</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">60.4</td>
            <td style="padding: 6px; font-weight: bold;">62.8</td>
            <td style="padding: 6px; font-weight: bold;">61.7</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">w/ $\mathcal{M}^\text{CS}$-d</td>
            <td style="padding: 6px;">64.1</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">52.8</td>
            <td style="padding: 6px;">61.8</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">61.7</td>
            <td style="padding: 6px;">48.0</td>
            <td style="padding: 6px;">42.5</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">w/ $\mathcal{M}^\text{CS}$-e</td>
            <td style="padding: 6px;">61.2</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">51.3</td>
            <td style="padding: 6px;">59.1</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">61.9</td>
            <td style="padding: 6px;">57.9</td>
            <td style="padding: 6px;">56.5</td>
          </tr>
          <tr style="background-color: #f0f7ff; font-weight: bold; border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">w/ $\mathcal{M}^\text{CS}$-f</td>
            <td style="padding: 6px;">65.6</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">53.7</td>
            <td style="padding: 6px;">63.5</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">61.8</td>
            <td style="padding: 6px;">55.2</td>
            <td style="padding: 6px;">49.7</td>
          </tr>
          <tr style="border-bottom: 1px solid #eee;">
            <td style="padding: 6px; text-align: left; border-right: 1px solid #eee;">w/ $\mathcal{M}^\text{CS}$-g</td>
            <td style="padding: 6px;">62.2</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">52.1</td>
            <td style="padding: 6px;">60.2</td>
            <td style="padding: 6px; border-right: 1px solid #eee;">58.9</td>
            <td style="padding: 6px;">59.4</td>
            <td style="padding: 6px;">59.1</td>
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
