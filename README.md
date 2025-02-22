 # UniVTG (ICCV'23)
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/univtg-towards-unified-video-language/highlight-detection-on-qvhighlights)](https://paperswithcode.com/sota/highlight-detection-on-qvhighlights?p=univtg-towards-unified-video-language) [![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/univtg-towards-unified-video-language/moment-retrieval-on-qvhighlights)](https://paperswithcode.com/sota/moment-retrieval-on-qvhighlights?p=univtg-towards-unified-video-language)

[[arXiv]](https://arxiv.org/abs/2307.16715) <a src="https://img.shields.io/badge/%F0%9F%A4%97-Open%20in%20Spaces-blue" href="https://huggingface.co/spaces/KevinQHLin/UniVTG">
    <img src="https://img.shields.io/badge/%F0%9F%A4%97-Open%20in%20Spaces-blue" alt="Open in Spaces">
<a src="https://img.shields.io/twitter/url?color=blue&label=Tweet&logo=twitter&url=https%3A%2F%2Ftwitter.com%2FKevinQHLin%2Fstatus%2F1649124447037841408" href="https://twitter.com/KevinQHLin/status/1686223119718006784">
    <img src="https://img.shields.io/twitter/url?color=blue&label=Tweet&logo=twitter&url=https%3A%2F%2Ftwitter.com%2FKevinQHLin%2Fstatus%2F1649124447037841408" alt="Tweet">
</a>
 
> **TL; DR:** The first video temporal grounding pretraining model, unifying diverse temporal annotations to power moment retrieval (interval), highlight detection (curve) and video summarization (point).

![UniVTG](figures/univtg_demo.gif)

### 📢 News
<!--  -->
- [2023.8.6] Create the [Huggingface space demo](https://huggingface.co/spaces/KevinQHLin/UniVTG)!
- [2023.7.31] We release the arXiv paper, codes, checkpoints, and gradio demo.

### 📝 Todo
- [ ] Connect UniVTG with LLM e.g., ChatGPT.
- [ ] Upload all downstream checkpoints.
- [x] Upload all pretraining checkpoints.

## 🌟 Run on your video:
To power practical usage, we release the following checkpoints:

*can be run on a single GPU with less than 4GB memory, highly efficient, less than 1 sec to perform temporal grounding even long video.*

> 
| Video Enc.  | Text Enc.  | Pretraining            | Fine-tuning   |  Checkpoints |
| ------------------ |  ------------------ | ------------------ | ------- | ---- |
| CLIP-B/16 | CLIP-B/16 | 4M      | -      |   [Google Drive](https://drive.google.com/drive/folders/1-eGata6ZPV0A1BBsZpYyIooos9yjMx2f?usp=sharing)  |
| CLIP-B/16 | CLIP-B/16 | 4M | QVHL + Charades + NLQ + TACoS + ActivityNet + DiDeMo      |  [Google Drive](https://drive.google.com/drive/folders/1l6RyjGuqkzfZryCC6xwTZsvjWaIMVxIO?usp=sharing)  

Download checkpoint and put it in the dir `results/omni`.

Download the example videos from [here](https://drive.google.com/drive/folders/1TpMYRmdAx5yx-lQu4ivCnAX67voUfBcL?usp=sharing) and put it under `examples/`

Run `python3 main_gradio.py --resume /results/omni/model_best.ckpt`

<details open><summary>[ Youtube video ]</summary><img src="./figures/case1.jpg" alt="Youtube video" style="width: 100%; height: auto;">
</details>
<details open><summary>[ Egocentric video ]</summary><img src="./figures/case3.jpg" alt="Egocentric video" style="width: 100%; height: auto;">
</details>
<details open><summary>[ Charades video  ]</summary><img src="./figures/case2.jpg" alt="Charades video" style="width: 100%; height: auto;">
</details>

## ⚙️ Preparation

Please find instructions in [install.md](install.md) to setup environment and datasets.

## 📦 Model Zoo

Download checkpoints in [model.md](model.md) to reproduce the benchmark results.

## 🎨 Visualization

If you want to draw visualizations like our paper, you can simply run `python3 plot/qvhl.py` to generate corresponding figures by providing the prediction json.

![visualization](figures/plot_qvhl.jpg)

## 🎓 Citation
If you find our work helps, please cite our paper.

```
@misc{lin2023univtg,
      title={UniVTG: Towards Unified Video-Language Temporal Grounding}, 
      author={Kevin Qinghong Lin and Pengchuan Zhang and Joya Chen and Shraman Pramanick and Difei Gao and Alex Jinpeng Wang and Rui Yan and Mike Zheng Shou},
      year={2023},
      eprint={2307.16715},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```

## ✉️ Contact
This repo is maintained by [Kevin](https://qinghonglin.github.io/). Questions and discussions are welcome via kevin.qh.lin@gmail.com or open an issue.

## 😊 Acknowledgement

This codebase is based on [moment_detr](https://github.com/jayleicn/moment_detr), [HERO_Video_Feature_Extractor](https://github.com/linjieli222/HERO_Video_Feature_Extractor), [UMT](https://github.com/tencentarc/umt).

We thank the authors for their open-source contributions.

## LICENSE
MIT
