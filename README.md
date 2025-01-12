<div align="center">
<h2 align="center"> <a href="https://arxiv.org/abs/2412.06171">
Holmes-VAU: Towards Long-term Video Anomaly Understanding at Any Granularity
</a></h2>

<h5 align="center"> If you like our project, please give us a star ⭐ on GitHub for latest update.  </h2>

</div>

##  :sparkles:Highlights
> **Abstract:** How can we enable models to comprehend video anomalies occurring over varying temporal scales and contexts? Traditional Video Anomaly Understanding (VAU) methods focus on frame-level anomaly prediction, often missing the interpretability of complex and diverse real-world anomalies. Recent multimodal approaches leverage visual and textual data but lack hierarchical annotations that capture both short-term and long-term anomalies.
<section class="hero teaser">
  <div class="container is-max-desktop">
    <div class="hero-body">
      <img src="assets/teaser.png" alt="MY ALT TEXT"/>
    </div>
  </div>
</section>

> To address this challenge, we introduce HIVAU-70k, a large-scale benchmark for hierarchical video anomaly understanding across any granularity. We develop a semi-automated annotation engine that efficiently scales high-quality annotations by combining manual video segmentation with recursive free-text annotation using large language models (LLMs). This results in over 70,000 multi-granular annotations organized at clip-level, event-level, and video-level segments.
<section class="hero teaser">
  <div class="container is-max-desktop">
    <div class="hero-body">
      <img src="assets/data_stastic.png" alt="MY ALT TEXT"/>
    </div>
  </div>
</section>

> For efficient anomaly detection in long videos, we propose the Anomaly-focused Temporal Sampler (ATS). ATS integrates an anomaly scorer with a density-aware sampler to adaptively select frames based on anomaly scores, ensuring that the multimodal LLM concentrates on anomaly-rich regions, which significantly enhances both efficiency and accuracy. Extensive experiments demonstrate that our hierarchical instruction data markedly improves anomaly comprehension. The integrated ATS and visual-language model outperform traditional methods in processing long videos.
<div align="center">
<section class="hero teaser">
  <div class="container is-max-desktop">
    <div class="hero-body">
      <img src="assets/framework.png" alt="MY ALT TEXT" style="width: 60%;"/>
    </div>
  </div>
</section>
</div>



## :date: TODO
- [x] Release the paper.
- [x] Release the HIVAU-70k annotations.
- [ ] Release the HolmesVAU model.
- [ ] Release the inference code.
- [ ] Release the training code.


## :wrench: Benchmarks
1. Download videos

Download the source videos for UCF-Crime and XD-Violence from the homepage below:
- [UCF-Crime](https://www.crcv.ucf.edu/projects/real-world/)
- [XD-Violence](https://roc-ng.github.io/XD-Violence/)

2. Check the folder

Put all their training videos and test videos in the `[ucf-crime/xd-violence]/videos/[train/test]` folder respectively. Please ensure the data structure is as below.
~~~~
├── HIVAU-70k
    ├── instruction
        ├── merge_instruction_test_final.jsonl
        └── merge_instruction_train_final.jsonl
    ├── raw_annotations
        ├── ucf_database_train.json
        ├── ucf_database_test.json
        ├── xd_database_train.json
        └── xd_database_test.json
    └── videos
        ├── ucf-crime
            ├── clips
            ├── events
            └── videos
                ├── train
                    ├── Abuse001_x264.mp4
                    ├── ...
                └── test
                    ├── Abuse028_x264.mp4
                    ├── ...
        └── xd-violence
            ├── clips
            ├── events
            └── videos
                ├── train
                    ├── A.Beautiful.Mind.2001__#00-01-45_00-02-50_label_A.mp4
                    ├── ...
                └── test
                    ├── A.Beautiful.Mind.2001__#00-25-20_00-29-20_label_A.mp4
                    ├── ...


~~~~

3. Split videos

This process consumes several hours:
```bash
cd HIVAU-70k
python split_video.py
python check_video.py
```

## Citation

If you find this repo useful for your research, please consider citing our papers:

```bibtex
@article{zhang2024holmesvau,
  title={Holmes-vau: Towards long-term video anomaly understanding at any granularity},
  author={Zhang, Huaxin and Xu, Xiaohao and Wang, Xiang and Zuo, Jialong and Huang, Xiaonan and Gao, Changxin and Zhang, Shanjun and Yu, Li and Sang, Nong},
  journal={arXiv preprint arXiv:2412.06171},
  year={2024}
}

@article{zhang2024holmesvad,
  title={Holmes-VAD: Towards Unbiased and Explainable Video Anomaly Detection via Multi-modal LLM},
  author={Zhang, Huaxin and Xu, Xiaohao and Wang, Xiang and Zuo, Jialong and Han, Chuchu and Huang, Xiaonan and Gao, Changxin and Wang, Yuehuan and Sang, Nong},
  journal={arXiv preprint arXiv:2406.12235},
  year={2024}
}
```
---

