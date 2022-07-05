# LMaaS-Papers
![](https://img.shields.io/github/last-commit/txsun1997/LMaaS-Papers?color=green) ![](https://img.shields.io/badge/PaperNumber-14-brightgreen)

A curated list of "Language-Model-as-a-Service (LMaaS)" papers

## Contents

- [Introduction](#introduction)
- [Keywords](#keywords)
- [Papers](#papers)
- [Contributing](#contributing)

## Introduction

(We are still completing this paper list. A detailed introduction to the LMaaS will be added soon.)

The paper list is mainly maintained by [Tianxiang Sun](https://txsun1997.github.io/). We strongly encourage the NLP researchers who are interested in this topic to make **pull request** to add or update the papers! (See [Contributing](#contributing))

## Keywords

We follow the same keywords convention as [PromptPapers](https://github.com/thunlp/PromptPapers).

![](https://img.shields.io/badge/GPT--3-blue) The abbreviation of the work.

![](https://img.shields.io/badge/Discrete_Prompt-red) The key feature of the work.

![](https://img.shields.io/badge/Zero--shot-green) The main experimental setting of the work.

## Papers

1. **To Tune or Not to Tune? Adapting Pretrained Representations to Diverse Tasks**. RepL4NLP@ACL 2019 ![](https://img.shields.io/badge/Feature--based-red) ![](https://img.shields.io/badge/Full--data-green) 

   *Matthew E. Peters, Sebastian Ruder, Noah A. Smith*. [[pdf](https://arxiv.org/abs/1903.05987)]

2. **Language Models as Knowledge Bases?** EMNLP 2019 ![](https://img.shields.io/badge/LAMA-blue) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Zero--shot-green)

   *Fabio Petroni, Tim Rocktäschel, Patrick Lewis, Anton Bakhtin, Yuxiang Wu, Alexander H. Miller, Sebastian Riedel*. [[pdf](https://arxiv.org/abs/1909.01066)] [[code](https://github.com/facebookresearch/LAMA)]

3. **How Can We Know What Language Models Know?** TACL 2020 ![](https://img.shields.io/badge/LPAQA-blue) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Zero--shot-green)

   *Zhengbao Jiang, Frank F. Xu, Jun Araki, Graham Neubig*. [[pdf](https://arxiv.org/abs/1911.12543)] [[code](https://github.com/jzbjyb/LPAQA)]

4. **Language Models are Few-Shot Learners.** NeurIPS 2020 ![](https://img.shields.io/badge/GPT--3-blue) ![](https://img.shields.io/badge/In--context_Learning-blue) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Zero--shot-green)![](https://img.shields.io/badge/Few--shot-green)

   *Tom B. Brown, Benjamin Mann, Nick Ryder, Melanie Subbiah, Jared Kaplan, Prafulla Dhariwal, Arvind Neelakantan, Pranav Shyam, Girish Sastry, Amanda Askell, Sandhini Agarwal, Ariel Herbert-Voss, Gretchen Krueger, Tom Henighan, Rewon Child, Aditya Ramesh, Daniel M. Ziegler, Jeffrey Wu, Clemens Winter, Christopher Hesse, Mark Chen, Eric Sigler, Mateusz Litwin, Scott Gray, Benjamin Chess, Jack Clark, Christopher Berner, Sam McCandlish, Alec Radford, Ilya Sutskever, Dario Amodei*. [[pdf](https://arxiv.org/abs/2005.14165)]

5. **Calibrate Before Use: Improving Few-Shot Performance of Language Models**. ICML 2021 ![](https://img.shields.io/badge/Calibrate_Before_Use-blue) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Few--shot-green)

   *Tony Z. Zhao, Eric Wallace, Shi Feng, Dan Klein, Sameer Singh*. [[pdf](https://arxiv.org/abs/2102.09690)] [[code](https://github.com/tonyzhaozh/few-shot-learning)]

6. **Multitask Prompted Training Enables Zero-Shot Task Generalization**. ICLR 2022 ![](https://img.shields.io/badge/T0-blue) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Zero--shot-green)

   *Victor Sanh, Albert Webson, Colin Raffel, Stephen H. Bach, Lintang Sutawika, Zaid Alyafeai, Antoine Chaffin, Arnaud Stiegler, Teven Le Scao, Arun Raja, Manan Dey, M Saiful Bari, Canwen Xu, Urmish Thakker, Shanya Sharma Sharma, Eliza Szczechla, Taewoon Kim, Gunjan Chhablani, Nihal Nayak, Debajyoti Datta, Jonathan Chang, Mike Tian-Jian Jiang, Han Wang, Matteo Manica, Sheng Shen, Zheng Xin Yong, Harshit Pandey, Rachel Bawden, Thomas Wang, Trishala Neeraj, Jos Rozen, Abheesht Sharma, Andrea Santilli, Thibault Fevry, Jason Alan Fries, Ryan Teehan, Tali Bers, Stella Biderman, Leo Gao, Thomas Wolf, Alexander M. Rush*. [[pdf](https://arxiv.org/abs/2110.08207)] [[code](https://github.com/bigscience-workshop/t-zero)]

7. **Learning To Retrieve Prompts for In-Context Learning**. NAACL-HLT 2022 ![](https://img.shields.io/badge/EPR-blue) ![](https://img.shields.io/badge/Prompt_Retrieval-red)

   *Ohad Rubin, Jonathan Herzig, Jonathan Berant*. [[pdf](https://arxiv.org/abs/2112.08633)] [[code](https://github.com/OhadRubin/EPR)]

8. **Black-Box Tuning for Language-Model-as-a-Service**. ICML 2022 ![](https://img.shields.io/badge/BBT-blue) ![](https://img.shields.io/badge/Soft_Prompt-red) ![](https://img.shields.io/badge/Few--shot-green)

   *Tianxiang Sun, Yunfan Shao, Hong Qian, Xuanjing Huang, Xipeng Qiu.* [[pdf](https://arxiv.org/abs/2201.03514)] [[code](https://github.com/txsun1997/Black-Box-Tuning)]

9. **Co-training Improves Prompt-based Learning for Large Language Models**. ICML 2022 ![](https://img.shields.io/badge/Co--training-blue) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Zero--shot-green) ![](https://img.shields.io/badge/Few--shot-green)

   *Hunter Lang, Monica Agrawal, Yoon Kim, David Sontag*. [[pdf](https://arxiv.org/abs/2202.00828)] 

10. **$\mathcal{Y}$-Tuning: An Efficient Tuning Paradigm for Large-Scale Pre-Trained Models via Label Representation Learning**. Preprint 2022.2 ![](https://img.shields.io/badge/Y--Tuning-blue) ![](https://img.shields.io/badge/Feature--based-red) ![](https://img.shields.io/badge/Full--data-green)

    *Yitao Liu, Chenxin An, Xipeng Qiu*. [[pdf](https://arxiv.org/abs/2202.09817)]

11. **Black-box Prompt Learning for Pre-trained Language Models**. Preprint 2022.1 ![](https://img.shields.io/badge/Soft_Prompt-red) ![](https://img.shields.io/badge/Full--data-green)

    *Shizhe Diao, Xuechun Li, Yong Lin, Zhichao Huang, Tong Zhang*. [[pdf](https://arxiv.org/abs/2201.08531)]

12. **GrIPS: Gradient-free, Edit-based Instruction Search for Prompting Large Language Models**. Preprint 2022.3 ![](https://img.shields.io/badge/GrIPS-blue) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Natural--Instructions-green)

    *Archiki Prasad, Peter Hase, Xiang Zhou, Mohit Bansal*. [[pdf](https://arxiv.org/abs/2203.07281)] [[code](https://github.com/archiki/GrIPS)]

13. **RLPrompt: Optimizing Discrete Text Prompts With Reinforcement Learning**. Preprint 2022.5 ![](https://img.shields.io/badge/RLPrompt-blue) ![](https://img.shields.io/badge/Discrete_Prompt-red) ![](https://img.shields.io/badge/Few--shot-green)

    *Mingkai Deng, Jianyu Wang, Cheng-Ping Hsieh, Yihan Wang, Han Guo, Tianmin Shu, Meng Song, Eric P. Xing, Zhiting Hu*. [[pdf](https://arxiv.org/abs/2205.12548)] [[code](https://github.com/mingkaid/rl-prompt)]

14. **BBTv2: Pure Black-Box Optimization Can Be Comparable to Gradient Descent for Few-Shot Learning**. Preprint 2022.5 ![](https://img.shields.io/badge/BBTv2-blue) ![](https://img.shields.io/badge/Soft_Prompt-red) ![](https://img.shields.io/badge/Few--shot-green)

    *Tianxiang Sun, Zhengfu He, Hong Qian, Xuanjing Huang, Xipeng Qiu*. [[pdf](https://arxiv.org/abs/2205.11200)] [[code](https://github.com/txsun1997/Black-Box-Tuning)]

## Contributing

:+1::tada: First off, thanks for taking the time to contribute! :tada::+1:

Steps to contribute:

- Make your awesome changes
- Submit pull request; if you add a new entry, please give a very brief explanation why you think it should be added.
