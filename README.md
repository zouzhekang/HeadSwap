<h1 align='center'>HeadSwap</h1>

**place your head automaticly.**  
⚠️  infact, I made a big mistake at my code, I'll resolve it and retrain an new weight, please wait some days...

## 📸 Showcase



## 📅️ TODO

| Status | Milestone |    ETA     |
| :----: | :---------------------------------------------------------------------------------------------------- | :--------: |
| 🚀 | **[Inference source code meet everyone on GitHub](https://github.com/zouzhekang/HeadSwap)** | comming soon |
| 🚀 | **[Pretrained model on Huggingface](https://huggingface.co/)**              | comming soon |
| 🚀 | **[Releasing data preparation and training scripts](#training)**                                                | TBD |
| 🚀 | **[ComfyUI support]()**                                                    | TBD |

## 🔧️ Framework

![framework](assets/framework.jpg)

## ⚙️ Installation

- System requirement: centos, Cuda 12.4
- Tested GPUs: A800

Create conda environment:

```bash
  conda create -n headswap python=3.10
  conda activate headswap
```

Install packages with `pip`

```bash
  pip install -r requirements.txt
```

## 🗝️️ Usage

The entry point for inference is `inference.py`. Before testing your cases, two preparations need to be completed:

1. [Download all required pretrained models](#download-pretrained-models).
2. [Prepare source image and driving audio pairs](#prepare-inference-data).
3. [Run inference](#run-inference).

### 📥 Download Pretrained Models

you can download [dwpose](https://huggingface.co/fudan-generative-ai/hallo/tree/main/hallo) and put it in ./pretrained_models/


Then you can easily get all pretrained models required by inference.py from HuggingFace repo.

Finally, these pretrained models should be organized as follows:

```text
./pretrained_models/
`-- DWPose/
    |-- dw-ll_ucoco_384.onnx
    `-- yolox_l.onnx
./insightface_model/
`-- models/
    `-- buffalo_l/
        |-- det_10g.onnx
        `-- w600k_r50.onnx
~/.cache/
`-- huggingface/
    `-- hub/
        |-- models--Qwen--Qwen-Image-Edit-2509
        `-- 
```

### 🛠️ Prepare Inference Data

We have provided [some samples](./assets/) for your reference.

### 🎮 Run Inference

Simply to run the `./inference.py` and pass `source_image` and `target_image` as input, You can pass `--output` to specify the output file name. 

```bash
python inference.py --source_image assets/source0.jpg --target_image assets/target0.jpg --output ./test.png
```  

## ⚠️ Social Risks and Mitigations

This project is intended solely for learning, communication, technical research, and legitimate creative expression. I'm fully aware that this technology carries serious social risks if misused to create false information or non-consensual synthetic content. Therefore, I strictly prohibit any form of illegal or malicious use, including but not limited to defaming others, committing fraud, or infringing on personal image rights. Users must comply with laws and regulations, ensure that they have obtained explicit authorization from relevant individuals, and clearly label any generated content. The developers of this project are not responsible for any consequences arising from the misuse of the code by users.  

本项目仅用于学习交流、技术研究与合法的创意表达。我深知该技术存在被滥用于制作虚假信息、非同意性合成内容等严重社会风险。因此，我严格禁止任何形式的非法或恶意用途，包括但不限于诋毁他人、实施欺诈或侵犯肖像权。请使用者务必遵守法律法规，确保已获得相关人物的明确授权，并对生成内容进行显著标识。本项目的开发者不承担由使用者滥用代码而引起的任何责任。  

## 🤗 Acknowledgements

I would like to thank the contributors to the [Qwen-Image](https://github.com/QwenLM/Qwen-Image), [DiffSynth-Studio](https://github.com/modelscope/DiffSynth-Studio), [insightface](https://github.com/deepinsight/insightface) and [dwpose](https://github.com/IDEA-Research/DWPose) repositories, for their open research and exploration.

If I missed any open-source projects or related articles, I would like to complement the acknowledgement of this specific work immediately.
