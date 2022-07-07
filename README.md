# Language Model as a Service (LMaaS)
![](https://img.shields.io/github/last-commit/txsun1997/LMaaS-Papers?color=green) ![](https://img.shields.io/badge/PaperNumber-32-brightgreen)

This is a curated list of "Language-Model-as-a-Service (LMaaS)" papers, which is mainly maintained by [Tianxiang Sun](https://txsun1997.github.io/). We strongly encourage the NLP researchers who are interested in this topic to make pull request to add or update the papers (See [Contributing](#contributing)). Watch this repository for the latest updates!

## Updates

- 2022/7/4: Create this paper list

## Contents

- [Introduction](#introduction)
  - [Scope](#scope)
  - [Advantages](#advantages)
- [Keywords](#keywords)
- [Papers](#papers)
  - [Text Prompt](#text-prompt)
  - [In-Context Learning](#in-context-learning)
  - [Black-Box Optimization](#black-box-optimization)
  - [Feature-based Learning](#feature-based-learning)
  - [Data Generation](#data-generation)
- [Contributing](#contributing)

## Introduction

Due to commercial reasons and expensive tuning cost, pre-trained large language models (LLMs) such as GPT-3 are usually released as a service instead of open sourcing model weights. We call this scenario "**Language-Model-as-a-Service (LMaaS)**". In such a scenario, users can access the powerful LLMs through their inference APIs. The service of LLMs has powered many use cases (See [GPT-3 Demo](https://gpt3demo.com/)). In contrast to fine-tuning, LMaaS allows a single general purpose LLM to serve many difference tasks and therefore is highly deployment-efficient. Nevertheless, how to adapt LLMs to target tasks without access to their parameters and gradients is a challenge. To make LLMs benefit a wider audience, we collect papers that fit into this scenario to facilitate future research. 

![](https://github.com/txsun1997/LMaaS-Papers/blob/main/img/LMaaS.png)

### Scope

Which papers fit into the scenario of LMaaS? We mainly consider papers that adapt LLMs to downstream tasks without accessing the model parameters and the gradients. Though fine-tuned LLMs can also be services after deployment, they are limited to solve a single task for limited audience. In our scope, we prefer serving general purpose models for a variety of users.

In existing literature, there are several lines of research that fit into LMaaS:

- **Text prompt**. By manually or automatically designing task-specific text prompts, users can solve the target task of interest by conditioning frozen LLMs.
- **In-context learning**. Users can provide a few examples in the input at inference time to help LLMs to rapidly adapt to the target task.
- **Black-box optimization**. By tuning a small portion of parameters (e.g., continuous prompt) with only the access of the LLM's output probability via black-box optimization, users can solve target tasks with a small training set.
- **Feature-based learning**. LLMs can serve as a feature extractor, on which users can build some learnable task-specific modules to perform classification or generation.
- **Data Generation**. Generative LLMs can be used to generate a dataset of labeled text pairs from scratch, which is then used to locally train a much smaller model.

**Note:** A related (and partially overlapped) topic is *prompt-based learning*, which aims to solve downstream tasks using general purpose LLMs by converting input and output with some template and verbalizer, respectively. However, most works in prompt-based learning require the access to model parameters and gradients, and therefore do not fit into our scope. For prompt-based learning papers that are not suitable for LMaaS, we recommend contributing to another awesome paper list: [PromptPaper](https://github.com/thunlp/PromptPapers).

### Advantages

Compared with fine-tuning task-specific LLMs, LMaaS has the following advantages:

- **Deployment-efficient**. LMaaS deploys a single general purpose LLM to serve various tasks. The target task can be performed conditioning the LLM with task-specific prompts, a small portion of parameters, or features. There is no need to maintain a copy of the entire model for each task.
- **Tuning-efficient**. When there is a small number of task-specific parameters to be tuned (e.g., black-box optimization), the optimization can be highly efficient since it does not require backpropagation, where the computation complexity is proportional to the model size and therefore can be expensive or even infeasible for LLMs. By contrast, the optimization complexity in LMaaS is independent of the model size.
- **Sample-efficient**. It has been demonstrated that LLMs can achieve competitive performance on a broad range of tasks with limited or even zero labeled data. Most works in LMaaS also focus on few-shot or zero-shot settings.

## Keywords

![](https://img.shields.io/badge/GPT--3-blue) The abbreviation of the work.

![](https://img.shields.io/badge/Discrete_Prompt-red) The key feature of the work.

![](https://img.shields.io/badge/Zero--shot-green) The main experimental setting of the work.

## Papers

### Text Prompt

1. **Language Models as Knowledge Bases?** EMNLP 2019 ![](https://img.shields.io/badge/LAMA-blue) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Zero--shot-green)

   *Fabio Petroni, Tim Rocktäschel, Patrick Lewis, Anton Bakhtin, Yuxiang Wu, Alexander H. Miller, Sebastian Riedel*. [[pdf](https://arxiv.org/abs/1909.01066)] [[code](https://github.com/facebookresearch/LAMA)]

2. **How Can We Know What Language Models Know?** TACL 2020 ![](https://img.shields.io/badge/LPAQA-blue) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Zero--shot-green)

   *Zhengbao Jiang, Frank F. Xu, Jun Araki, Graham Neubig*. [[pdf](https://arxiv.org/abs/1911.12543)] [[code](https://github.com/jzbjyb/LPAQA)]

3. **Language Models are Few-Shot Learners.** NeurIPS 2020 ![](https://img.shields.io/badge/GPT--3-blue) ![](https://img.shields.io/badge/In--context_Learning-red) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Zero--shot-green)![](https://img.shields.io/badge/Few--shot-green)

   *Tom B. Brown, Benjamin Mann, Nick Ryder, Melanie Subbiah, Jared Kaplan, Prafulla Dhariwal, Arvind Neelakantan, Pranav Shyam, Girish Sastry, Amanda Askell, Sandhini Agarwal, Ariel Herbert-Voss, Gretchen Krueger, Tom Henighan, Rewon Child, Aditya Ramesh, Daniel M. Ziegler, Jeffrey Wu, Clemens Winter, Christopher Hesse, Mark Chen, Eric Sigler, Mateusz Litwin, Scott Gray, Benjamin Chess, Jack Clark, Christopher Berner, Sam McCandlish, Alec Radford, Ilya Sutskever, Dario Amodei*. [[pdf](https://arxiv.org/abs/2005.14165)]

4. **Multitask Prompted Training Enables Zero-Shot Task Generalization**. ICLR 2022 ![](https://img.shields.io/badge/T0-blue) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Zero--shot-green)

   *Victor Sanh, Albert Webson, Colin Raffel, Stephen H. Bach, Lintang Sutawika, Zaid Alyafeai, Antoine Chaffin, Arnaud Stiegler, Teven Le Scao, Arun Raja, Manan Dey, M Saiful Bari, Canwen Xu, Urmish Thakker, Shanya Sharma Sharma, Eliza Szczechla, Taewoon Kim, Gunjan Chhablani, Nihal Nayak, Debajyoti Datta, Jonathan Chang, Mike Tian-Jian Jiang, Han Wang, Matteo Manica, Sheng Shen, Zheng Xin Yong, Harshit Pandey, Rachel Bawden, Thomas Wang, Trishala Neeraj, Jos Rozen, Abheesht Sharma, Andrea Santilli, Thibault Fevry, Jason Alan Fries, Ryan Teehan, Tali Bers, Stella Biderman, Leo Gao, Thomas Wolf, Alexander M. Rush*. [[pdf](https://arxiv.org/abs/2110.08207)] [[code](https://github.com/bigscience-workshop/t-zero)]

5. **GrIPS: Gradient-free, Edit-based Instruction Search for Prompting Large Language Models**. Preprint 2022.3 ![](https://img.shields.io/badge/GrIPS-blue) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Natural_Instructions-green)

   *Archiki Prasad, Peter Hase, Xiang Zhou, Mohit Bansal*. [[pdf](https://arxiv.org/abs/2203.07281)] [[code](https://github.com/archiki/GrIPS)]

6. **RLPrompt: Optimizing Discrete Text Prompts With Reinforcement Learning**. Preprint 2022.5 ![](https://img.shields.io/badge/RLPrompt-blue) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Few--shot-green)

   *Mingkai Deng, Jianyu Wang, Cheng-Ping Hsieh, Yihan Wang, Han Guo, Tianmin Shu, Meng Song, Eric P. Xing, Zhiting Hu*. [[pdf](https://arxiv.org/abs/2205.12548)] [[code](https://github.com/mingkaid/rl-prompt)]

7. **Large Language Models are Zero-Shot Reasoners**. Preprint 2022.6 ![](https://img.shields.io/badge/Let's_think_step_by_step-blue) ![](https://img.shields.io/badge/Chain_of_Thought-red) ![](https://img.shields.io/badge/Zero--shot-green)

   *Takeshi Kojima, Shixiang Shane Gu, Machel Reid, Yutaka Matsuo, Yusuke Iwasawa*. [[pdf](https://arxiv.org/abs/2205.11916)] [[code](https://github.com/kojima-takeshi188/zero_shot_cot)]

8. **Zero-Shot Video Question Answering via Frozen Bidirectional Language Models**. Preprint 2022.6 ![](https://img.shields.io/badge/FrozenBiLM-blue) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Zero--shot-green)

   *Antoine Yang, Antoine Miech, Josef Sivic, Ivan Laptev, Cordelia Schmid*. [[pdf](https://arxiv.org/abs/2206.08155)] [[code](https://antoyang.github.io/frozenbilm.html)]

### In-Context Learning

1. **Language Models are Few-Shot Learners.** NeurIPS 2020 ![](https://img.shields.io/badge/GPT--3-blue) ![](https://img.shields.io/badge/In--context_Learning-red) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Zero--shot-green)![](https://img.shields.io/badge/Few--shot-green)

   *Tom B. Brown, Benjamin Mann, Nick Ryder, Melanie Subbiah, Jared Kaplan, Prafulla Dhariwal, Arvind Neelakantan, Pranav Shyam, Girish Sastry, Amanda Askell, Sandhini Agarwal, Ariel Herbert-Voss, Gretchen Krueger, Tom Henighan, Rewon Child, Aditya Ramesh, Daniel M. Ziegler, Jeffrey Wu, Clemens Winter, Christopher Hesse, Mark Chen, Eric Sigler, Mateusz Litwin, Scott Gray, Benjamin Chess, Jack Clark, Christopher Berner, Sam McCandlish, Alec Radford, Ilya Sutskever, Dario Amodei*. [[pdf](https://arxiv.org/abs/2005.14165)]

2. **Calibrate Before Use: Improving Few-Shot Performance of Language Models**. ICML 2021 ![](https://img.shields.io/badge/Calibrate_Before_Use-blue) ![](https://img.shields.io/badge/In--context_Learning-red) ![](https://img.shields.io/badge/Few--shot-green)

   *Tony Z. Zhao, Eric Wallace, Shi Feng, Dan Klein, Sameer Singh*. [[pdf](https://arxiv.org/abs/2102.09690)] [[code](https://github.com/tonyzhaozh/few-shot-learning)]

3. **An Explanation of In-context Learning as Implicit Bayesian Inference**. ICLR 2022 ![](https://img.shields.io/badge/Implicit_Bayesian_Inference-blue) ![](https://img.shields.io/badge/In--context_Learning-red) ![](https://img.shields.io/badge/Few--shot-green)

   *Sang Michael Xie, Aditi Raghunathan, Percy Liang, Tengyu Ma*. [[pdf](https://openreview.net/forum?id=RdJVFCHjUMI)] [[code](https://github.com/p-lambda/incontext-learning)]

4. **Fantastically Ordered Prompts and Where to Find Them: Overcoming Few-Shot Prompt Order Sensitivity**. ACL 2022 ![](https://img.shields.io/badge/In--context_Learning-red) ![](https://img.shields.io/badge/Few--shot-green)

   *Yao Lu, Max Bartolo, Alastair Moore, Sebastian Riede, Pontus Stenetorp*. [[pdf](https://arxiv.org/abs/2104.08786)]

5. **Noisy Channel Language Model Prompting for Few-Shot Text Classification**. ACL 2022 ![](https://img.shields.io/badge/Channel_LM-blue) ![](https://img.shields.io/badge/In--context_Learning-red) ![](https://img.shields.io/badge/Few--shot-green)

   *Sewon Min, Mike Lewis, Hannaneh Hajishirzi, Luke Zettlemoyer*. [[pdf](https://arxiv.org/abs/2108.04106)] [[code](https://github.com/shmsw25/Channel-LM-Prompting)]

6. **What Makes Good In-Context Examples for GPT-3?** DeeLIO@ACL 2022 ![](https://img.shields.io/badge/In--context_Learning-red)

   Jiachang Liu, Dinghan Shen, Yizhe Zhang, Bill Dolan, Lawrence Carin, Weizhu Chen. [[pdf](https://arxiv.org/abs/2101.06804)] 

7. **Learning To Retrieve Prompts for In-Context Learning**. NAACL 2022 ![](https://img.shields.io/badge/EPR-blue) ![](https://img.shields.io/badge/In--context_Learning-red)

   *Ohad Rubin, Jonathan Herzig, Jonathan Berant*. [[pdf](https://arxiv.org/abs/2112.08633)] [[code](https://github.com/OhadRubin/EPR)]

8. **MetaICL: Learning to Learn In Context**. NAACL 2022 ![](https://img.shields.io/badge/MetaICL-blue) ![](https://img.shields.io/badge/In--context_Learning-red) ![](https://img.shields.io/badge/Few--shot-green)

   *Sewon Min, Mike Lewis, Luke Zettlemoyer, Hannaneh Hajishirzi*. [[pdf](https://arxiv.org/abs/2110.15943)] [[code](https://github.com/facebookresearch/metaicl)]

9. **Improving In-Context Few-Shot Learning via Self-Supervised Training**. NAACL 2022 ![](https://img.shields.io/badge/In--context_Learning-red) ![](https://img.shields.io/badge/Few--shot-green)

   *Mingda Chen, Jingfei Du, Ramakanth Pasunuru, Todor Mihaylov, Srini Iyer, Veselin Stoyanov, Zornitsa Kozareva*. [[pdf](https://arxiv.org/abs/2205.01703)]

10. **Rethinking the Role of Demonstrations: What Makes In-Context Learning Work?** Preprint 2022.2 ![](https://img.shields.io/badge/In--context_Learning-red) ![](https://img.shields.io/badge/Few--shot-green)

   *Sewon Min, Xinxi Lyu, Ari Holtzman, Mikel Artetxe, Mike Lewis, Hannaneh Hajishirzi, Luke Zettlemoyer*. [[pdf](https://arxiv.org/abs/2202.12837)] [[code](https://github.com/alrope123/rethinking-demonstrations)]

11. **In-Context Learning for Few-Shot Dialogue State Tracking.** Preprint 2022.3 ![](https://img.shields.io/badge/Codex-blue) ![](https://img.shields.io/badge/In--context_Learning-red)  ![](https://img.shields.io/badge/Zero--shot-green) ![](https://img.shields.io/badge/Few--shot-green)

    *Yushi Hu, Chia-Hsuan Lee, Tianbao Xie, Tao Yu, Noah A. Smith, Mari Ostendorf* [[pdf](https://arxiv.org/abs/2203.08568)] [[code](https://https//github.com/Yushi-Hu/IC-DST)]

12. **Benchmarking Generalization via In-Context Instructions on 1,600+ Language Tasks**. Preprint 2022.4 ![](https://img.shields.io/badge/Natural_Instructions-blue) ![](https://img.shields.io/badge/In--context_Learning-red) ![](https://img.shields.io/badge/Few--shot-green)

    *Yizhong Wang, Swaroop Mishra, Pegah Alipoormolabashi, Yeganeh Kordi, Amirreza Mirzaei, Anjana Arunkumar, Arjun Ashok, Arut Selvan Dhanasekaran, Atharva Naik, David Stap, Eshaan Pathak, Giannis Karamanolakis, Haizhi Gary Lai, Ishan Purohit, Ishani Mondal, Jacob Anderson, Kirby Kuznia, Krima Doshi, Maitreya Patel, Kuntal Kumar Pal, Mehrad Moradshahi, Mihir Parmar, Mirali Purohit, Neeraj Varshney, Phani Rohitha Kaza, Pulkit Verma, Ravsehaj Singh Puri, Rushang Karia, Shailaja Keyur Sampat, Savan Doshi, Siddhartha Mishra, Sujan Reddy, Sumanta Patro, Tanay Dixit, Xudong Shen, Chitta Baral, Yejin Choi, Noah A. Smith, Hannaneh Hajishirzi, Daniel Khashabi*. [[pdf](https://arxiv.org/abs/2204.07705)] [[code](https://github.com/allenai/natural-instructions)]

13. **Can language models learn from explanations in context?** Preprint 2022.4 ![](https://img.shields.io/badge/In--context_Learning-red)  ![](https://img.shields.io/badge/Zero--shot-green) ![](https://img.shields.io/badge/Few--shot-green)

    *Andrew K. Lampinen, Ishita Dasgupta, Stephanie C. Y. Chan, Kory Matthewson, Michael Henry Tessler, Antonia Creswell, James L. McClelland, Jane X. Wang, Felix Hill*. [[pdf](https://arxiv.org/abs/2204.02329)]

### Black-Box Optimization

1. **Black-Box Tuning for Language-Model-as-a-Service**. ICML 2022 ![](https://img.shields.io/badge/BBT-blue) ![](https://img.shields.io/badge/Soft_Prompt-red) ![](https://img.shields.io/badge/Few--shot-green)

   *Tianxiang Sun, Yunfan Shao, Hong Qian, Xuanjing Huang, Xipeng Qiu.* [[pdf](https://arxiv.org/abs/2201.03514)] [[code](https://github.com/txsun1997/Black-Box-Tuning)]

2. **Black-box Prompt Learning for Pre-trained Language Models**. Preprint 2022.1 ![](https://img.shields.io/badge/Soft_Prompt-red) ![](https://img.shields.io/badge/Full--data-green)

   *Shizhe Diao, Xuechun Li, Yong Lin, Zhichao Huang, Tong Zhang*. [[pdf](https://arxiv.org/abs/2201.08531)]

3. **GrIPS: Gradient-free, Edit-based Instruction Search for Prompting Large Language Models**. Preprint 2022.3 ![](https://img.shields.io/badge/GrIPS-blue) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Natural_Instructions-green)

   *Archiki Prasad, Peter Hase, Xiang Zhou, Mohit Bansal*. [[pdf](https://arxiv.org/abs/2203.07281)] [[code](https://github.com/archiki/GrIPS)]

4. **RLPrompt: Optimizing Discrete Text Prompts With Reinforcement Learning**. Preprint 2022.5 ![](https://img.shields.io/badge/RLPrompt-blue) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Few--shot-green)

   *Mingkai Deng, Jianyu Wang, Cheng-Ping Hsieh, Yihan Wang, Han Guo, Tianmin Shu, Meng Song, Eric P. Xing, Zhiting Hu*. [[pdf](https://arxiv.org/abs/2205.12548)] [[code](https://github.com/mingkaid/rl-prompt)]

5. **BBTv2: Pure Black-Box Optimization Can Be Comparable to Gradient Descent for Few-Shot Learning**. Preprint 2022.5 ![](https://img.shields.io/badge/BBTv2-blue) ![](https://img.shields.io/badge/Soft_Prompt-red) ![](https://img.shields.io/badge/Few--shot-green)

   *Tianxiang Sun, Zhengfu He, Hong Qian, Xuanjing Huang, Xipeng Qiu*. [[pdf](https://arxiv.org/abs/2205.11200)] [[code](https://github.com/txsun1997/Black-Box-Tuning)]

6. **Few-shot Prompting Towards Controllable Response Generation**. Preprint 2022.6 ![](https://img.shields.io/badge/Soft_Prompt-red) ![](https://img.shields.io/badge/Few--shot-green)

   *Hsuan Su, Pohan Chi, Shih-Cheng Huang, Chung Ho Lam, Saurav Sahay, Shang-Tse Chen, Hung-yi Lee*. [[pdf](https://arxiv.org/abs/2206.03931)]

### Feature-based Learning

1. **To Tune or Not to Tune? Adapting Pretrained Representations to Diverse Tasks**. RepL4NLP@ACL 2019 ![](https://img.shields.io/badge/Feature--based-red) ![](https://img.shields.io/badge/Full--data-green) 

   *Matthew E. Peters, Sebastian Ruder, Noah A. Smith*. [[pdf](https://arxiv.org/abs/1903.05987)]

2. **Co-training Improves Prompt-based Learning for Large Language Models**. ICML 2022 ![](https://img.shields.io/badge/Co--training-blue) ![](https://img.shields.io/badge/Feature--based-red) ![](https://img.shields.io/badge/Zero--shot-green) ![](https://img.shields.io/badge/Few--shot-green)

   *Hunter Lang, Monica Agrawal, Yoon Kim, David Sontag*. [[pdf](https://arxiv.org/abs/2202.00828)] 

3. **Y-Tuning: An Efficient Tuning Paradigm for Large-Scale Pre-Trained Models via Label Representation Learning**. Preprint 2022.2 ![](https://img.shields.io/badge/Y--Tuning-blue) ![](https://img.shields.io/badge/Feature--based-red) ![](https://img.shields.io/badge/Full--data-green)

   *Yitao Liu, Chenxin An, Xipeng Qiu*. [[pdf](https://arxiv.org/abs/2202.09817)]

4. **LST: Ladder Side-Tuning for Parameter and Memory Efficient Transfer Learning**. Preprint 2022.6 ![](https://img.shields.io/badge/LST-blue) ![](https://img.shields.io/badge/Feature--based-red) ![](https://img.shields.io/badge/Full--data-green)

   *Yi-Lin Sung, Jaemin Cho, Mohit Bansal*. [[pdf](https://arxiv.org/abs/2206.06522)] [[code](https://github.com/ylsung/Ladder-Side-Tuning)]

### Data Generation
1. **Generating Datasets with Pretrained Language Models**. EMNLP 2021 ![](https://img.shields.io/badge/Dino-blue) ![](https://img.shields.io/badge/Data_Generation-red) ![](https://img.shields.io/badge/Zero--shot-green)

   *Timo Schick, Hinrich Schütze*. [[pdf](https://arxiv.org/abs/2104.07540)] [[code](https://github.com/timoschick/dino)]

2. **ZeroGen: Efficient Zero-shot Learning via Dataset Generation**. Preprint 2022.2 ![](https://img.shields.io/badge/ZeroGen-blue) ![](https://img.shields.io/badge/Data_Generation-red) ![](https://img.shields.io/badge/Zero--shot-green)

   *Jiacheng Ye, Jiahui Gao, Qintong Li, Hang Xu, Jiangtao Feng, Zhiyong Wu, Tao Yu, Lingpeng Kong*. [[pdf](https://arxiv.org/abs/2202.07922)] [[code](https://github.com/jiacheng-ye/ZeroGen)]

3. **Generating Training Data with Language Models: Towards Zero-Shot Language Understanding**. Preprint 2022.2 ![](https://img.shields.io/badge/SuperGen-blue) ![](https://img.shields.io/badge/Data_Generation-red) ![](https://img.shields.io/badge/Zero--shot-green)

   *Yu Meng, Jiaxin Huang, Yu Zhang, Jiawei Han* [[pdf](http://arxiv.org/abs/2202.04538)] [[code](https://github.com/yumeng5/SuperGen)]

4. **ZeroGen+: Self-Guided High-Quality Data Generation in Efficient Zero-Shot Learning**. Preprint 2022.2 ![](https://img.shields.io/badge/ZeroGen+-blue) ![](https://img.shields.io/badge/Data_Generation-red) ![](https://img.shields.io/badge/Zero--shot-green)

   *Jiahui Gao, Renjie Pi, Yong Lin, Hang Xu, Jiacheng Ye, Zhiyong Wu, Xiaodan Liang, Zhenguo Li, Lingpeng Kong*. [[pdf](https://arxiv.org/abs/2205.12679)]


## Contributing

:+1::tada: First off, thanks for taking the time to contribute! :tada::+1:

Steps to contribute:

- Add a new paper or update an existing paper. Please check if your added paper fits into the [scope](#scope) of this repo.
- Please use the same format as existing entries. When adding keywords tags, please follow the same [keywords convention](#keywords). When adding the pdf link of the paper, please use the abstract page if it is on arXiv.
- Modify the `PaperNumber` on the top of the page accordingly and submit your pull request. We recommend giving a very brief explanation why you think a paper should be added or changed.

### Contributors

We thank all the contributors for paper recommendation!

<a href="https://github.com/txsun1997/LMaaS-Papers/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=txsun1997/LMaaS-Papers" />
</a>

