---
project: Paddle
stars: 22838
description: PArallel Distributed Deep LEarning: Machine Learning Framework from Industrial Practice （『飞桨』核心框架，深度学习&机器学习高性能单机、分布式训练和跨平台部署）
url: https://github.com/PaddlePaddle/Paddle
---

* * *

English | 简体中文 | 日本語

Welcome to the PaddlePaddle GitHub.

PaddlePaddle, as the first independent R&D deep learning platform in China, has been officially open-sourced to professional communities since 2016. It is an industrial platform with advanced technologies and rich features that cover core deep learning frameworks, basic model libraries, end-to-end development kits, tools & components as well as service platforms. PaddlePaddle originates from industrial practices with dedication and commitments to industrialization. It has been widely adopted by a wide range of sectors including manufacturing, agriculture, enterprise service, and so on while serving more than 18.08 million developers, 430,000 companies and generating 1,010,000 models. With such advantages, PaddlePaddle has helped an increasing number of partners commercialize AI.

Installation
------------

### Latest PaddlePaddle Release: 3.0

Our vision is to enable deep learning for everyone via PaddlePaddle. Please refer to our release announcement to track the latest features of PaddlePaddle.

### Install Latest Stable Release

# CPU
pip install paddlepaddle
# GPU
pip install paddlepaddle-gpu

For more information about installation, please view Quick Install

**PaddlePaddle New Generation Framework 3.0**
---------------------------------------------

-   **Unified Dynamic/Static Graphs and Automatic Parallelism**
    
    By requiring only minimal tensor partitioning annotations based on a single-card configuration, PaddlePaddle automatically discovers the most efficient distributed parallel strategy. This significantly reduces the costs of industrial development and training, enabling developers to focus more intently on model and algorithm innovation.
    
-   **Integrated Training and Inference for Large Models**
    
    The same framework supports both training and inference, achieving code reuse and seamless integration between these stages. This provides a unified development experience and maximum training efficiency for the entire large model workflow, offering the industry a superior development experience.
    
-   **High-Order Differentiation for Scientific Computing**
    
    Provides capabilities such as high-order automatic differentiation, complex number operations, Fourier transforms, compilation optimization, and distributed training support. It facilitates scientific exploration in fields including mathematics, mechanics, materials science, meteorology, and biology, substantially improving the speed of solving differential equations.
    
-   **Neural Network Compiler**
    
    Adopting an integrated framework design, it supports efficient training and flexible inference for diverse models, including generative and scientific computing models. It achieves an effective balance between computational flexibility and high performance, significantly lowering performance optimization costs.
    
-   **Heterogeneous Multi-Chip Adaptation** Features a mature and complete unified adaptation solution for multiple hardware types. Through standardized interfaces, it abstracts the variations in development interfaces across different chip software stacks, realizing a pluggable architecture.
    

Documentation
-------------

We provide English and Chinese documentation.

-   Guides
    
    You might want to start from how to implement deep learning basics with PaddlePaddle.
    
-   Practice
    
    So far you have already been familiar with Fluid. And the next step should be building a more efficient model or inventing your original Operator.
    
-   API Reference
    
    Our new API enables much shorter programs.
    
-   How to Contribute
    
    We appreciate your contributions!
    

Open Source Community
---------------------

-   Github Issues: bug reports, feature requests, install issues, usage issues, etc.
-   Many of our contribution events offer varying levels of mentorship from experienced community members, please check the events in the pinned issues, and consider attending.
-   Community Blog: https://pfcc.blog/
-   See more details about PaddlePaddle community at community.

Copyright and License
---------------------

PaddlePaddle is provided under the Apache-2.0 license.
