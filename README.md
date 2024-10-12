# Diffusion-Study
Diffusion 일기장


## Contents
- [Posts](#Posts)
- [Papers](#Papers)
  - [Diffusion Must Read](#Diffusion-Must-Read)
  - [Video](#Video) 
  - [Inpainting](#Inpainting)
- [Tutorial & Jupyter](#Tutorial-&-Jupyter)

# Experiments

- [Stable-Diffusion Finetuning](#Stable-Diffusion-Finetune)

## Stable-Diffusion-Finetune

### LoRA
- in diffusers/examples/text_to_image 디렉토리

- Training
```
accelerate launch train_text_to_image_lora_sdxl.py --pretrained_model_name_or_path="stabilityai/stable-diffusion-xl-base-1.0" --pretrained_vae_model_name_or_path="madebyollin/sdxl-vae-fp16-fix" --dataset_name="AdamLucek/oldbookillustrations-small" --validation_prompt="An inventor tinkers with a complex machine in his workshop, oblivious to the setting sun outside" --num_validation_images=4 --validation_epochs=1 --output_dir="output" --resolution=1024 --center_crop --random_flip --train_text_encoder --train_batch_size=1 --num_train_epochs=10 --checkpointing_steps=500 --gradient_accumulation_steps=4 --learning_rate=1e-04 --lr_warmup_steps=0 --report_to="wandb" --dataloader_num_workers=8 --allow_tf32 --mixed_precision="fp16" --hub_model_id="sdxl-lora-testing"
```

- Inference
[jupyter](diffusers/examples/text_to_image/finetune_inference.ipynb)

# Posts & Videos

**ratsgo's blog** \
딥러닝 기초 내용들 참고하기 좋은 블로그 \
[[Link](https://ratsgo.github.io/generative%20model/2018/01/27/VAE/)] 

**gaussian37** \
Computer Vision 기초 내용 \
[[Link](https://gaussian37.github.io/)] 

**What are Diffusion Models?** \
Diffusion 기초, 전반적인 내용 정리 \
[[Link](https://lilianweng.github.io/lil-log/2021/07/11/diffusion-models.html)] 

**How Diffusion Models work: the math from scratch** \
Diffusion 기초, 전반적인 내용 정리2 \
[[Link](https://theaisummer.com/diffusion-models/?fbclid=IwAR1BIeNHqa3NtC8SL0sKXHATHklJYphNH-8IGNoO3xZhSKM_GYcvrrQgB0o)] 

**DDPM Paper review** \
DDPM 논문 리뷰 블로그 \
[[Link](https://process-mining.tistory.com/188)] 

**Diffusion 논문 리뷰** \
Diffusion 필수 논문 리뷰 영상 \
[[Youtube1](https://youtu.be/jaPPALsUZo8)] 
[[Youtube2](https://youtu.be/KzrdkZUrbPk)]
[[Youtube3](https://youtu.be/Ec569AV6YD8)] 

# Papers
## Diffusion Must Read

**Denoising Diffusion Probabilistic Models** :heavy_check_mark: \
NeurIPS 2020. [[Paper](https://arxiv.org/abs/2006.11239)] [[Github](https://github.com/hojonathanho/diffusion)] \
Jonathan Ho, Ajay Jain, Pieter Abbeel \
19 Jun 2020

**Denoising Diffusion Implicit Models** :heavy_check_mark: \
ICLR 2021. [[Paper](https://arxiv.org/abs/2010.02502) [Github](https://github.com/ermongroup/ddim)] \
Jiaming Song, Chenlin Meng, Stefano Ermon \
Standford University \
6 Oct 2020

**Diffusion Models Beat GANs on Image Synthesis** :heavy_check_mark: \
arXiv 2021. [[Paper](https://arxiv.org/abs/2105.05233)] [[Github](https://github.com/openai/guided-diffusion)] \
Prafulla Dhariwal, Alex Nichol \
OpenAI \
11 May 2021

**Generative Modeling by Estimating Gradients of the Data Distribution** \
NeurIPS 2019. [[Paper](https://arxiv.org/abs/1907.05600)] [[Github](https://github.com/ermongroup/ncsn)] \
Yang Song, Stefano Ermon \
12 Jul 2019 

**Score-Based Generative Modeling through Stochastic Differential Equations** :heavy_check_mark: \
ICLR 2021. [[Paper](https://arxiv.org/abs/2011.13456)] [[Github](https://github.com/yang-song/score_sde)] \
Yang Song, Jascha Sohl-Dickstein, Diederik P. Kingma, Abhishek Kumar, Stefano Ermon, Ben Poole \
Stanford University | Google Brain \
26 Nov 2020

**Classifier-Free Diffusion Guidance** \
NeurIPS Workshop 2021. [[Paper](https://arxiv.org/abs/2207.12598)] \
Jonathan Ho, Tim Salimans \
Google Research, Brain team \
28 Sep 2021

**Diffusion-GAN: Training GANs with Diffusion** \
arXiv 2022. [[Paper](https://arxiv.org/abs/2206.02262)] \
Zhendong Wang, Huangjie Zheng, Pengcheng He, Weizhu Chen, Mingyuan Zhou \
The University of Texas at Austin | Microsoft Azure AI \
11 Oct 2022

**Improved Denoising Diffusion Probabilistic Models** \
ICLR 2021. [[Paper](https://arxiv.org/abs/2102.09672)] [[Github](https://github.com/openai/improved-diffusion)] \
Alex Nichol, Prafulla Dhariwal \
OpenAI \
18 Feb 2021

**Tackling the Generative Learning Trilemma with Denoising Diffusion GANs** :heavy_check_mark: \
ICLR 2022. [[Paper](https://arxiv.org/abs/2112.07804)] [[Page](https://nvlabs.github.io/denoising-diffusion-gan/)] [[Github](https://github.com/NVlabs/denoising-diffusion-gan)] \
Zhisheng Xiao, Karsten Kreis, Arash Vahdat \
The University of Chicago | NVIDIA \
15 Dec 2021

**High-Resolution Image Synthesis with Latent Diffusion Models (Stable Diffusion)** :heavy_check_mark:  \
arXiv 2021. [[Paper](https://arxiv.org/abs/2112.10752)] [[Github](https://github.com/CompVis/latent-diffusion)] \
Robin Rombach, Andreas Blattmann, Dominik Lorenz, Patrick Esser, Björn Ommer \
Ludwig Maximilian University of Munich & IWR, Heidelberg University, Germany | Runway ML \
20 Dec 2021


## Video

**Video Diffusion Models** :heavy_check_mark: \
arXiv 2022. [[Paper](https://arxiv.org/abs/2204.03458)] [[Github](https://github.com/lucidrains/video-diffusion-pytorch)]  \
Jonathan Ho, Tim Salimans, Alexey Gritsenko, William Chan, Mohammad Norouzi, David J. Fleet \
Google Research, Brain Team \
7 Apr 2022

**Diffusion Models for Video Prediction and Infilling** :heavy_check_mark: \
TMLR 2022. [[Paper](https://arxiv.org/abs/2206.07696)] [[Github](https://github.com/Tobi-r9/RaMViD)]
Tobias Höppe, Arash Mehrjou, Stefan Bauer, Didrik Nielsen, Andrea Dittadi \
15 Jun 2022

**MCVD: Masked Conditional Video Diffusion for Prediction, Generation, and Interpolation** :heavy_check_mark: \
NeurIPS 2022. [[Paper](https://arxiv.org/abs/2205.09853)] [[Github](https://github.com/voletiv/mcvd-pytorch)] \
Vikram Voleti, Alexia Jolicoeur-Martineau, Christopher Pal \
19 May 2022

## Inpainting

**Repaint: RePaint: Inpainting using Denoising Diffusion Probabilistic Models** :heavy_check_mark: \
CVPR 2022. [[Paper](https://arxiv.org/abs/2201.09865)] [[Github](https://github.com/andreas128/RePaint)] \
Andreas Lugmayr, Martin Danelljan, Andres Romero, Fisher Yu, Radu Timofte, Luc Van Gool \
Computer Vision Lab, ETH Zurich, Switzerland \
24 Jan 2022 


# Tutorial & Jupyter

DDPM 기초 구현 \
[[Youtube](https://youtu.be/a4Yfz2FxXiY)]

Diffusion Huggingface \
[[Colab](https://colab.research.google.com/github/huggingface/notebooks/blob/main/diffusers/diffusers_intro.ipynb)]
