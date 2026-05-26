<h1 align="center">CT-SpatialVQA</h1>

CT-SpatialVQA is a benchmark for evaluating **semantic-spatial reasoning** in 3D CT derived from CT-RATE radiology reports and volumes.

Key dataset facts:
- 1,601 radiology reports / CT volumes (CT-RATE test split)
- 9,077 spatially grounded QA pairs
- LLM-assisted validation with 95% human consensus agreement rate

<p align="center">
  <img src="Figures/ct_spatial_vqa_pipeline.jpg" width="92%" alt="CT-SpatialVQA pipeline"/>
</p>

## What CT-SpatialVQA Tests

Questions are designed to require explicit spatial grounding, including:
- anatomical localization
- laterality awareness
- relative position (3D)
- adjacency vs. containment
- spatial extent / boundaries

Spatial categories (as used in the paper):
- Laterality & Bilateral Symmetry
- Longitudinal (Vertical) Position
- Anterior-Posterior (Depth) Relations
- Medial-Lateral Orientation (Centricity)
- Adjacency & Containment
- Spatial Extent & Boundaries

## Dataset

The dataset is provided in `dataset/`. It includes:
- final filtered QA pairs (JSON)
- generic JSONL exports with `case_id`, `image_path`, `question`, `answer`

JSONL schema:
```json
{"case_id":"...","image_path":"...","question":"...","answer":"..."}
```

## CT Volumes

This repository distributes QA pairs and paths, but **not** the CT volumes themselves. A CT-RATE download script is included in `dataset/` (matching the provided JSONLs).

## Technical Details

Benchmarking and pipeline implementation details are documented in `benchmarking/` and `QA_generation/`.

## References

This repository uses the CT-RATE dataset and benchmarks prior 3D medical VLMs.

<details>
<summary><b>BibTeX</b></summary>

```bibtex
@article{ct-rate,
  title={Generalist foundation models from a multimodal dataset for 3D computed tomography},
  author={Hamamci, Ibrahim Ethem and Er, Sezgin and Wang, Chenyu and Almas, Furkan and Simsek, Ayse Gulnihan and Esirgun, Sevval Nil and Dogan, Irem and Durugol, Omer Faruk and Hou, Benjamin and Shit, Suprosanna and others},
  journal={Nature Biomedical Engineering},
  pages={1--19},
  year={2026},
  publisher={Nature Publishing Group UK London}
}

@article{med3dvlm,
  title={Med3dvlm: An efficient vision-language model for 3d medical image analysis},
  author={Xin, Yu and Ates, Gorkem Can and Gong, Kuang and Shao, Wei},
  journal={IEEE Journal of Biomedical and Health Informatics},
  year={2025},
  publisher={IEEE}
}

@article{m3d,
  title={M3d: Advancing 3d medical image analysis with multi-modal large language models},
  author={Bai, Fan and Du, Yuxin and Huang, Tiejun and Meng, Max Q-H and Zhao, Bo},
  journal={arXiv preprint arXiv:2404.00578},
  year={2024}
}

@article{merlin,
  title={Merlin: A vision language foundation model for 3d computed tomography},
  author={Blankemeier, Louis and Cohen, Joseph Paul and Kumar, Ashwin and Van Veen, Dave and Gardezi, Syed Jamal Safdar and Paschali, Magdalini and Chen, Zhihong and Delbrouck, Jean-Benoit and Reis, Eduardo and Truyts, Cesar and others},
  journal={Research Square},
  pages={rs--3},
  year={2024}
}

@article{radfm,
  title={Towards generalist foundation model for radiology by leveraging web-scale 2d\\&3d medical data},
  author={Wu, Chaoyi and Zhang, Xiaoman and Zhang, Ya and Hui, Hui and Wang, Yanfeng and Xie, Weidi},
  journal={Nature Communications},
  volume={16},
  number={1},
  pages={7866},
  year={2025},
  publisher={Nature Publishing Group UK London}
}

@inproceedings{vila,
  title={Vila-m3: Enhancing vision-language models with medical expert knowledge},
  author={Nath, Vishwesh and Li, Wenqi and Yang, Dong and Myronenko, Andriy and Zheng, Mingxin and Lu, Yao and Liu, Zhijian and Yin, Hongxu and Law, Yee Man and Tang, Yucheng and others},
  booktitle={Proceedings of the Computer Vision and Pattern Recognition Conference},
  pages={14788--14798},
  year={2025}
}

@article{lingshu,
  title={Lingshu: A generalist foundation model for unified multimodal medical understanding and reasoning},
  author={Xu, Weiwen and Chan, Hou Pong and Li, Long and Aljunied, Mahani and Yuan, Ruifeng and Wang, Jianyu and Xiao, Chenghao and Chen, Guizhen and Liu, Chaoqun and Li, Zhaodonghui and others},
  journal={arXiv preprint arXiv:2506.07044},
  year={2025}
}

@misc{google2026medgemma,
  title        = {MedGemma 1.5 Model Card},
  author       = {{Google Research}},
  year         = {2026},
  url          = {https://huggingface.co/google/medgemma-1.5-4b-it},
  note         = {Accessed: 2026-02-22},
  organization = {Google},
}
```

</details>
