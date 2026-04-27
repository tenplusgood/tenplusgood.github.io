---
layout: default
permalink: /a-harness-page/
title: "Affordance Agent Harness: Verification-Gated Skill Orchestration"
---

<style>
  .paper-title {
    font-family: "MyFont", Verdana, sans-serif;
    letter-spacing: 2px;
    font-size: 42px;
    margin: 32px 10px;
    text-align: center;
    color: #000000;
    font-weight: bold;
    line-height: 1.2;
  }
  .authors-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 15px;
    margin-bottom: 10px;
  }
  .author-btn {
    display: inline-flex;
    align-items: center;
    padding: 5px 10px;
    border-radius: 20px;
    background: transparent;
    color: #3273dc;
    text-decoration: none;
    transition: all 0.3s;
  }
  .author-btn:hover {
    background: #f0f0f0;
    color: #848484;
  }
  .author-avatar {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    margin-right: 8px;
    box-shadow: #b7b7b7 0px 0px 3px 1px;
    object-fit: cover;
  }
  .author-name {
    font-size: 18px;
  }
  .author-sup {
    color: #606266;
    margin-left: 3px;
    font-size: 12px;
  }
  .affiliations-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 15px;
    margin-bottom: 10px;
  }
  .affil-btn {
    display: inline-flex;
    align-items: center;
    padding: 5px 10px;
    color: #3273dc;
    text-decoration: none;
  }
  .affil-icon {
    width: 24px;
    height: 24px;
    margin-right: 6px;
  }
  .affil-name {
    font-size: 18px;
    color: #333;
  }
  .con-cor {
    font-family: Arial;
    font-size: 14px;
    margin: 18px 0px;
    text-align: center;
    color: #606266;
  }
  .guidance-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 15px;
    margin-bottom: 40px;
  }
  .guidance-btn {
    display: inline-flex;
    align-items: center;
    padding: 10px 20px;
    border-radius: 25px;
    background: #444444;
    color: #ffffff !important;
    text-decoration: none;
    box-shadow: #d8d8d8 1px 1px 1px 1px;
    transition: all 0.3s;
  }
  .guidance-btn:hover {
    opacity: 0.8;
  }
  .guidance-btn i {
    font-size: 18px;
    margin-right: 8px;
  }
  .guidance-btn-text {
    font-size: 18px;
  }
  .content-container {
    max-width: 900px;
    margin: 0 auto;
    padding: 0 20px;
  }
  .section-title {
    font-family: "MyFont", Verdana, sans-serif;
    letter-spacing: 2px;
    font-size: 28px;
    margin-top: 40px;
    margin-bottom: 20px;
    text-align: center;
    font-weight: bold;
  }
  .text-content {
    font-size: 16px;
    line-height: 1.75rem;
    text-align: justify;
    margin-bottom: 20px;
  }
  .teaser-img {
    width: 80%;
    display: block;
    margin: 0 auto;
    border-radius: 10px;
    box-shadow: 1px 1px 4px 1px #afafaf;
  }
  .table-container {
    overflow-x: auto;
    margin: 20px auto;
    display: flex;
    justify-content: center;
  }
  table {
    border-collapse: collapse;
    width: max-content;
    max-width: 100%;
    margin: 0 auto;
  }
  thead {
    border-bottom: 1px solid #000;
    border-top: 2px solid #000;
  }
  tbody tr:last-child {
    border-bottom: 2px solid #000;
  }
  th, td {
    padding: 8px 1rem;
    text-align: center;
  }
  .bibtex-box {
    background: #f2f2f2;
    border-radius: 5px;
    padding: 15px;
    font-family: 'Consolas', monospace;
    font-size: 14px;
    overflow-x: auto;
    line-height: 1.4rem;
  }
  hr.divider {
    border: 0;
    border-top: 1px solid #dcdfe6;
    margin: 40px 0;
  }
  .news-alert {
    background-color: #f0f9eb;
    color: #67c23a;
    padding: 8px 16px;
    border-radius: 4px;
    text-align: center;
    margin-bottom: 20px;
    font-size: 14px;
  }
</style>

<div class="content-container">

  <!-- 最新消息提示 -->
  <div class="news-alert">
    <i class="fas fa-fire" style="color: #f56c6c;"></i> This template is based on the Vue Academic Project Page Template style.
  </div>

  <!-- 文章标题 -->
  <h1 class="paper-title">
    Affordance Agent Harness: Verification-Gated Skill Orchestration
  </h1>

  <!-- 作者名单 -->
  <div class="authors-container">
    <a href="https://jethrojames.github.io/" class="author-btn">
      <img src="https://ui-avatars.com/api/?name=Haojian+Huang&background=random" class="author-avatar" alt="Haojian Huang">
      <span class="author-name">Haojian Huang<sup class="author-sup">1,2*</sup></span>
    </a>
    <a href="https://tenplusgood.github.io/" class="author-btn">
      <img src="https://ui-avatars.com/api/?name=Jiahao+Shi&background=random" class="author-avatar" alt="Jiahao Shi">
      <span class="author-name">Jiahao Shi<sup class="author-sup">2,3*</sup></span>
    </a>
    <a href="#" class="author-btn">
      <img src="https://ui-avatars.com/api/?name=Yinchuan+Li&background=random" class="author-avatar" alt="Yinchuan Li">
      <span class="author-name">Yinchuan Li<sup class="author-sup">1,2</sup></span>
    </a>
    <a href="#" class="author-btn">
      <img src="https://ui-avatars.com/api/?name=Yingcong+Chen&background=random" class="author-avatar" alt="Yingcong Chen">
      <span class="author-name">Yingcong Chen<sup class="author-sup">1,2†</sup></span>
    </a>
  </div>

  <!-- 地址名单 -->
  <div class="affiliations-container">
    <span class="affil-btn">
      <span class="affil-name"><sup class="author-sup">1</sup>HKUST(GZ)</span>
    </span>
    <span class="affil-btn">
      <span class="affil-name"><sup class="author-sup">2</sup>Knowin</span>
    </span>
    <span class="affil-btn">
      <span class="affil-name"><sup class="author-sup">3</sup>Harbin Engineering University</span>
    </span>
  </div>

  <!-- 共一和通讯提示内容 -->
  <div class="con-cor">
    *: Equal Contribution. †: Corresponding Author.
  </div>

  <!-- 提供引导按钮 -->
  <div class="guidance-container">
    <a href="https://arxiv.org/abs/2511.21021" class="guidance-btn">
      <i class="fas fa-file-pdf"></i>
      <span class="guidance-btn-text">Paper</span>
    </a>
    <a href="#" class="guidance-btn">
      <i class="fab fa-github"></i>
      <span class="guidance-btn-text">Code</span>
    </a>
    <a href="#" class="guidance-btn">
      <i class="fas fa-video"></i>
      <span class="guidance-btn-text">Video</span>
    </a>
    <a href="#" class="guidance-btn">
      <i class="fas fa-database"></i>
      <span class="guidance-btn-text">Dataset</span>
    </a>
  </div>

  <!-- Teaser 展示图 -->
  <img src="{{ '/images/comp.png' | relative_url }}" class="teaser-img" alt="A-Harness Teaser">
  <p style="text-align: center; margin-top: 15px; font-style: italic; color: #666; font-size: 14px;">
    A-Harness: A verification-gated runtime that unifies heterogeneous skills with adaptive routing and episodic memory.
  </p>

  <hr class="divider">

  <!-- Abstract 摘要卡片 -->
  <h2 class="section-title">Abstract</h2>
  <p class="text-content">
    Affordance grounding requires identifying <em>where</em> and <em>how</em> an agent should interact in open-world scenes, where actionable regions are often small, occluded, reflective, and visually ambiguous. Recent systems therefore combine multiple skills (e.g., detection, segmentation, interaction-imagination), yet most orchestrate them with fixed pipelines that are poorly matched to per-instance difficulty, offer limited targeted recovery from intermediate errors, and fail to amortize experience over recurring objects. We observe that many failures stem not from the lack of stronger models but from the lack of a system-level ability to actively acquire and <strong>validate</strong> evidence under bounded inference cost, where "verification" must rely on relative signals rather than ground-truth labels at test time. To this end, we propose <strong>Affordance Agent Harness</strong>, a closed-loop runtime that unifies heterogeneous skills with an evidence store and cost control, retrieves episodic memories to provide priors for recurring categories, and employs a Router to adaptively select and parameterize skills. Crucially, an affordance-specific Verifier <strong>gates commitments</strong> using self-consistency, cross-scale stability, and evidence sufficiency, triggering targeted retries when needed before a final judge fuses accumulated evidence and trajectories into the prediction. Experiments on multiple affordance benchmarks and difficulty-controlled subsets demonstrate a superior accuracy–cost Pareto frontier over fixed-pipeline baselines, improving grounding quality while reducing average skill calls and latency.
  </p>

  <hr class="divider">

  <!-- Motivation 核心动力 -->
  <h2 class="section-title">Motivation</h2>
  <p class="text-content">
    Affordance grounding remains brittle when decisions must be geometry-aware and evidence must be aggregated coherently across heterogeneous cues and tools. Existing agent systems exhibit three limitations: (1) <strong>Fixed Execution</strong>: they execute skills in a predetermined order regardless of input complexity; (2) <strong>Lack of Closed-loop Correction</strong>: they lack a mechanism to diagnose failure sources and re-invoke responsible skills when intermediate outputs conflict; (3) <strong>No Persistent Experience</strong>: recurring objects are re-solved from scratch each time. 
  </p>
  <p class="text-content">
    We reframes affordance grounding as a budgeted, evidence-seeking decision process, where tool usage is a per-instance policy rather than a static script. We rely on three families of relative signals: (i) <strong>cross-tool consistency</strong>, (ii) <strong>cross-scale stability</strong>, and (iii) <strong>evidence sufficiency</strong>.
  </p>

  <hr class="divider">

  <!-- Methodology 核心方法 -->
  <h2 class="section-title">Methodology</h2>
  <img src="{{ '/images/skills.pdf' | relative_url }}" class="teaser-img" alt="Methodology" onerror="this.onerror=null; this.src='{{ '/images/comp.png' | relative_url }}';">
  <p style="text-align: center; margin-top: 15px; font-size: 14px; color: #666;">
    If the PDF is not displaying, you can <a href="{{ '/images/skills.pdf' | relative_url }}" target="_blank" style="color: #3273dc;">click here to view it</a>.
  </p>
  
  <p class="text-content" style="margin-top: 20px;">
    A-Harness consists of four key components:
  </p>
  <ul class="text-content" style="padding-left: 20px;">
    <li style="margin-bottom: 10px;"><strong>Evidence Store with Provenance</strong>: Accumulates heterogeneous skill outputs (boxes, masks, text) tagged with their source and zoom level to enable cross-skill agreement checks.</li>
    <li style="margin-bottom: 10px;"><strong>Two-Tier Memory</strong>: A <em>Common-sense Bank</em> for stable priors of frequent objects and a <em>Test-time Episodic Bank</em> that accumulates verifier-accepted successful trajectories for online adaptation.</li>
    <li style="margin-bottom: 10px;"><strong>Budget-Aware Router</strong>: Selects the next skill and its parameters by choosing the action most likely to resolve current uncertainty per unit cost (benefit-cost ratio).</li>
    <li style="margin-bottom: 10px;"><strong>Verifier</strong>: Sidesteps the absence of ground truth by using relative diagnostics (consistency, stability, sufficiency) to gate commitments and trigger <strong>targeted retries</strong>.</li>
  </ul>

  <hr class="divider">

  <!-- Results 实验结果 -->
  <h2 class="section-title">Quantitative Results</h2>
  
  <h3 style="text-align: center; font-family: 'MyFont', Verdana, sans-serif; margin-bottom: 15px;">Results on ReasonAff & UMD</h3>
  <div class="table-container">
    <table>
      <thead>
        <tr>
          <th rowspan="2">Model</th>
          <th colspan="2">ReasonAff</th>
          <th colspan="2">UMD</th>
        </tr>
        <tr>
          <th>gIoU</th>
          <th>cIoU</th>
          <th>gIoU</th>
          <th>cIoU</th>
        </tr>
      </thead>
      <tbody>
        <tr style="color: #888;">
          <td style="text-align: left;">VLPart</td>
          <td>4.21</td>
          <td>3.88</td>
          <td>--</td>
          <td>--</td>
        </tr>
        <tr style="color: #888;">
          <td style="text-align: left;">OVSeg</td>
          <td>16.52</td>
          <td>10.59</td>
          <td>--</td>
          <td>--</td>
        </tr>
        <tr style="color: #888;">
          <td style="text-align: left;">SAN</td>
          <td>10.21</td>
          <td>13.45</td>
          <td>--</td>
          <td>--</td>
        </tr>
        <tr>
          <td style="text-align: left;">LISA-7B</td>
          <td>38.17</td>
          <td>40.58</td>
          <td>41.90</td>
          <td>41.23</td>
        </tr>
        <tr>
          <td style="text-align: left;">SAM4MLLM</td>
          <td>45.51</td>
          <td>33.64</td>
          <td>12.40</td>
          <td>8.41</td>
        </tr>
        <tr>
          <td style="text-align: left;">AffordanceLLM</td>
          <td>48.49</td>
          <td>38.61</td>
          <td>43.11</td>
          <td>38.97</td>
        </tr>
        <tr>
          <td style="text-align: left;">InternVL3-8B/7B</td>
          <td>31.79</td>
          <td>24.68</td>
          <td>30.46</td>
          <td>28.73</td>
        </tr>
        <tr>
          <td style="text-align: left;">Qwen2.5VL-7B</td>
          <td>25.18</td>
          <td>20.54</td>
          <td>33.21</td>
          <td>29.83</td>
        </tr>
        <tr>
          <td style="text-align: left;">AffordanceVLM</td>
          <td>30.50</td>
          <td>25.54</td>
          <td>25.41</td>
          <td>17.96</td>
        </tr>
        <tr>
          <td style="text-align: left;">Seg-Zero</td>
          <td>59.26</td>
          <td>48.03</td>
          <td>44.26</td>
          <td>39.30</td>
        </tr>
        <tr>
          <td style="text-align: left;">Vision Reasoner</td>
          <td>63.04</td>
          <td>52.70</td>
          <td>44.00</td>
          <td>39.71</td>
        </tr>
        <tr>
          <td style="text-align: left;">Affordance-R1</td>
          <td>67.41</td>
          <td>62.72</td>
          <td>49.85</td>
          <td>42.24</td>
        </tr>
        <tr style="border-top: 1px solid #eee;">
          <td style="text-align: left; font-style: italic;">Full Fixed Skill Chain</td>
          <td>55.05</td>
          <td>49.57</td>
          <td>50.19</td>
          <td>49.24</td>
        </tr>
        <tr style="background-color: #f0f9eb; font-weight: bold;">
          <td style="text-align: left;">A-Harness (Claude-Opus)</td>
          <td>69.68</td>
          <td>70.88</td>
          <td>54.94</td>
          <td>55.04</td>
        </tr>
        <tr style="background-color: #f0f9eb; font-weight: bold;">
          <td style="text-align: left;">A-Harness (Qwen-3.5)</td>
          <td>58.51</td>
          <td>49.47</td>
          <td>57.61</td>
          <td>53.39</td>
        </tr>
      </tbody>
    </table>
  </div>

  <h3 style="text-align: center; font-family: 'MyFont', Verdana, sans-serif; margin-top: 40px; margin-bottom: 15px;">Zero-shot comparison on RAGNet (3DOI & HANDAL)</h3>
  <div class="table-container">
    <table>
      <thead>
        <tr>
          <th rowspan="2">Method</th>
          <th colspan="2">3DOI</th>
          <th colspan="2">HANDAL-easy</th>
          <th colspan="2">HANDAL-hard</th>
        </tr>
        <tr>
          <th>gIoU</th>
          <th>cIoU</th>
          <th>gIoU</th>
          <th>cIoU</th>
          <th>gIoU</th>
          <th>cIoU</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td style="text-align: left;">G-DINO</td>
          <td>4.1</td>
          <td>3.9</td>
          <td>3.6</td>
          <td>3.0</td>
          <td>3.4</td>
          <td>3.1</td>
        </tr>
        <tr>
          <td style="text-align: left;">LISA</td>
          <td>12.3</td>
          <td>8.1</td>
          <td>15.5</td>
          <td>11.9</td>
          <td>12.3</td>
          <td>8.1</td>
        </tr>
        <tr>
          <td style="text-align: left;">GLaMM</td>
          <td>4.4</td>
          <td>2.9</td>
          <td>4.7</td>
          <td>3.5</td>
          <td>5.0</td>
          <td>3.5</td>
        </tr>
        <tr>
          <td style="text-align: left;">Vision-Reasoner</td>
          <td>39.6</td>
          <td>30.3</td>
          <td>29.6</td>
          <td>19.8</td>
          <td>27.7</td>
          <td>16.7</td>
        </tr>
        <tr>
          <td style="text-align: left;">Affordance-R1</td>
          <td>39.0</td>
          <td>33.4</td>
          <td>43.1</td>
          <td>38.7</td>
          <td>40.7</td>
          <td>37.9</td>
        </tr>
        <tr>
          <td style="text-align: left;">AffordanceVLM</td>
          <td>38.1</td>
          <td>39.4</td>
          <td>58.3</td>
          <td>58.1</td>
          <td>58.2</td>
          <td>57.8</td>
        </tr>
        <tr style="border-top: 1px solid #eee; background-color: #f9f9f9;">
          <td style="text-align: left; font-style: italic;">A-Harness (w/o M-CS)</td>
          <td>56.5</td>
          <td>47.2</td>
          <td>58.4</td>
          <td>57.6</td>
          <td>55.3</td>
          <td>55.1</td>
        </tr>
        <tr style="background-color: #f0f9eb; font-weight: bold;">
          <td style="text-align: left;">A-Harness (Full)</td>
          <td>65.6</td>
          <td>53.7</td>
          <td>63.5</td>
          <td>61.8</td>
          <td>55.2</td>
          <td>49.7</td>
        </tr>
      </tbody>
    </table>
  </div>

  <h3 style="text-align: center; font-family: 'MyFont', Verdana, sans-serif; margin-top: 40px; margin-bottom: 15px;">Ablation Study on ReasonAff & UMD</h3>
  <div class="table-container">
    <table>
      <thead>
        <tr>
          <th rowspan="2">Configuration</th>
          <th colspan="2">ReasonAff</th>
          <th colspan="2">UMD</th>
        </tr>
        <tr>
          <th>gIoU</th>
          <th>cIoU</th>
          <th>gIoU</th>
          <th>cIoU</th>
        </tr>
      </thead>
      <tbody>
        <tr style="background-color: #f9f9f9; font-weight: bold;">
          <td style="text-align: left;">Full Standard Config (GPT-4o)</td>
          <td>60.53</td>
          <td>54.91</td>
          <td>52.74</td>
          <td>50.04</td>
        </tr>
        <tr style="border-top: 1px solid #eee;">
          <td style="text-align: left;">w/ Rex-omni</td>
          <td>55.44</td>
          <td>52.73</td>
          <td>50.37</td>
          <td>41.78</td>
        </tr>
        <tr>
          <td style="text-align: left;">w/ Qwen2.5VL-7B-Instruct</td>
          <td>54.13</td>
          <td>51.12</td>
          <td>39.09</td>
          <td>38.57</td>
        </tr>
        <tr>
          <td style="text-align: left;">w/ Qwen-3.5-397B-A17B</td>
          <td>62.56</td>
          <td>56.27</td>
          <td>54.15</td>
          <td>53.82</td>
        </tr>
        <tr>
          <td style="text-align: left;">w/ SAM-3</td>
          <td>61.90</td>
          <td>56.36</td>
          <td>53.18</td>
          <td>50.56</td>
        </tr>
        <tr style="border-top: 1px solid #eee;">
          <td style="text-align: left;">Only w/ Det. & Seg. skill</td>
          <td>59.68</td>
          <td>49.29</td>
          <td>50.82</td>
          <td>41.92</td>
        </tr>
        <tr>
          <td style="text-align: left;">w/o Verifier (Router only)</td>
          <td>52.28</td>
          <td>43.15</td>
          <td>50.87</td>
          <td>42.00</td>
        </tr>
        <tr>
          <td style="text-align: left;">w/o $\mathcal{M}^{CS}$</td>
          <td>54.43</td>
          <td>53.38</td>
          <td>50.31</td>
          <td>43.12</td>
        </tr>
        <tr>
          <td style="text-align: left;">w/o $\mathcal{M}^{TT}$</td>
          <td>50.85</td>
          <td>41.89</td>
          <td>49.50</td>
          <td>41.04</td>
        </tr>
        <tr>
          <td style="text-align: left;">w/o $\mathcal{M}^{CS}$ & $\mathcal{M}^{TT}$</td>
          <td>49.41</td>
          <td>39.05</td>
          <td>48.98</td>
          <td>42.10</td>
        </tr>
      </tbody>
    </table>
  </div>

  <hr class="divider">

  <!-- BibTeX 引用 -->
  <h2 class="section-title">BibTeX</h2>
  <div class="bibtex-box">
<pre><code>@article{huang2026aharness,
  title={Affordance Agent Harness: Verification-Gated Skill Orchestration},
  author={Huang, Haojian and Shi, Jiahao and Li, Yinchuan and Chen, Yingcong},
  journal={Submitted to ECCV},
  year={2026}
}</code></pre>
  </div>

</div>
