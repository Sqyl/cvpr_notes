# **CVPR-Diffusion Model粗读**

这里简单存放了对近年CVPR中Diffusion Model相关论文的中英文标题和中文摘要，并对各篇论文主攻方向进行了简易的标注。

有关论文资源详情，请查阅<a href="https://github.com/amusi/CVPR2024-Papers-with-Code/blob/master/README.md">CVPR2024-Papers-with-Code</a>

## CVPR 2024



- **InstanceDiffusion: Instance-level Control for Image Generation**

- **[InstanceDiffusion：图像生成的实例级控制]<sup>*T2I, ControlDM*</sup>**

   本文引入了InstanceDiffusion（ID），它为文本到图像的扩散模型（Diffusion Model）添加了精确的实例级控制。ID 支持每个实例的自由形式语言条件，并允许以灵活的方式指定实例位置，如简单的单点、涂鸦、边界框或复杂的实例分割掩码及其组合。通过对T2I模型的三项重大更改来实现精确的实例级控制：UniFusion模块支持文本到图像模型的实例级条件，ScaleU模块提高了图像保真度，Multi-instance Sampler（多实例采样器）改进了多个实例的生成。



- **Residual Denoising Diffusion Models**

- **[残差去噪扩散模型]<sup>*IRestore*</sup>**

   一种新颖的双扩散过程，将传统的单去噪扩散过程解耦为残差扩散和噪声扩散。通过引入残差的方式，将最初无法解释图像恢复（Image Restoration）的基于去噪的扩散模型（DDIM， DDPM）扩展为用于图像生成和恢复的统一且可解释的模型。残差优先考虑确定性，噪声强调多样性，事的RDDM能够有效地统一具有不同确定性或多样性要求的任务。（数学描述太多了，先摆烂了，但是这个工作真的牛B）



- **DeepCache: Accelerating Diffusion Models for Free**

- **[DeepCache：免费加速扩散模型]<sup>*SpeedUp*</sup>**

   本文介绍了DeepCache，一种新颖的免训练范式，从模型架构的角度加速扩散模型（Diffusion Model）。利用在扩散模型的顺序去噪步骤中观察到的固有时间冗余，跨相邻去噪阶段缓存和检索特征，从而减少冗余计算。SD1.5加速系数提高了2.3倍，LDM-4-G加速系数提高4.1倍，但质量仅略有下降。



- **DEADiff: An Efficient Stylization Diffusion Model with Disentangled Representations**

- **[DEADiff：一种具有解缠结表示的高效风格化扩散模型]<sup>*ST*</sup>**

   本文引入DEADiff，解决了当前基于编码器方法在传输图像风格时显著减弱文本到图像（T2I）模型的文本可控性问题。本模型通过以下两种策略解决这个问题：1）将参考图像的风格和语义解耦。首先由Q-Formers提取解耦的特征表示，Q-Formers由不同的文本描述指导，然后将它们注入到交叉注意力层（Cross-Attention）中的互斥子集中，以更好实现解耦。2）非重构性学习方法。Q-Formers使用配对图像（并非相同的目标）进行训练，其中参考图像和标准答案（Ground-Truth）图像具有相同的风格或语义。



- **SVGDreamer: Text Guided SVG Generation with Diffusion Model**

- **[SVGDreamer：使用扩散模型生成文本引导的 SVG]<sup>*SVG, ControlDM*</sup>**

   本文提出了一种新颖的文本引导矢量图形合成方法，称为SVGDreamer。它结合了语义驱动的图像矢量化（SIVE）过程，可以将合成分解为前景对象和背景，从而增强可编辑性。



- **InteractDiffusion: Interaction-Control for Text-to-Image Diffusion Model**

- **[InteractDiffusion：文本到图像扩散模型的交互控制]<sup>*T2I, ControlDM*</sup>**

   本文提出了一种可插入的交互控制模型，称为InteractDiffusion，它扩展了现有的预训练T2I扩散模型（Diffusion Model），使它们能够更好地适应交互。首先对HOI信息进行标记，并通过交互嵌入来了解它们的关系。训练调节自注意力层（Self-attention Layer）将HOI标记映射到视觉标记，从而在现有T2I扩散模型中更好地调节视觉标记，并控制现有T2I扩散模型的相互作用和位置。



- **MMA-Diffusion: MultiModal Attack on Diffusion Models**

- **[MMA-扩散：对扩散模型的多模态攻击]<sup>*Safety*</sup>**

   本文引入MMA-Diffusion，通过有效规避当前在开源模型和商业在线服务中的防御措施，对T2I模型的安全构成重大而现实的威胁。它利用文本和视觉的方式绕过提示过滤器和事后安全检查器等保护措施，暴露出现有防御机制的漏洞。可以帮助防治生成不适当或不安全工作（NSFW）内容。

ps：港中文和华为教你如何用AI干坏事，比如做川普的裸图
<img src="https://github.com/Sqyl/cvpr_notes/blob/main/trump.png"/>



- **VMC: Video Motion Customization using Temporal Attention Adaption for Text-to-Video Diffusion Models**

- **[VMC：使用时间注意力适应文本到视频扩散模型的视频运动定制]<sup>*Video*</sup>**

   本文提出了视频运动定制（Video Motion Customization，VMC）框架，这是一种新颖的一次性调整方法，旨在适应视频扩散模型中的时间注意力层（Temporal Attention Layers），引入了一种新颖的运动蒸馏（？）目标，使用连续帧之间的残差向量作为运动参考。然后，扩散过程保留低频运动轨迹，同时减轻图像空间中与高频运动无关的噪声。





## CVPR 2023

- **Imagic: Text-Based Real Image Editing with Diffusion Models**

- **[Imagic：使用扩散模型进行基于文本的真实图像编辑]<sup>*T2I*</sup>**

   本文首次展示了将复杂文本（例如：非刚性）引导的语义编辑应用于单个真实图像的能力。模型仅需要输入单个图像和目标文本（用于编辑），并将对真实图像进行操作，而不需要任何额外的输入。这个方法被称为“Imagic”， 它利用预先训练（Pre-trained）的文本到图像（T2I）扩散模型（Diffusion Model）来完成此任务，通过生成与输入图像和目标文本对齐的文本嵌入，同时微调了扩散模型，以捕获图像特定的意义表示。




