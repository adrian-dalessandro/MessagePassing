---
layout: post
title: "Equivariant Losses & Weakly Supervised Localization"
tagline: "TODO"
author: Adrian D'Alessandro
excerpt_separator: <!--more-->
tags: localization weak supervision
---

Weakly supervised object localization (WSOL) is the very challenging task of identifying and grouping the regions of an image that contain some object of interest when the only information you have is that the object of interest is present within the image. Perhaps you have a whole bunch of images of horses and dogs, and you want to figure out exactly which pixels in an image belong to the dogs and which pixels belong the horses -- BUT you only know if an image contains a horse or a dog. You haven't been told where they are. It's an interesting problem!

[//]:  # (Maybe put a picture here?)

So, what are the major limitations that make this problem challenging and what are potential solutions? Here, I want to talk about equivariant losses and their applications.

### The Ill-posedness of Weakly Supervised Object Localization
It's useful here to find a way to describe the class of problem that we're dealing with when attempting to solve WSOL. The French mathematician Hadamard provides the concept of a well-posed problem that outlines 3 very useful properties for describing problems that we would like to model. These properties are:
1. A solution exists for any data relevant to the problem.
2. The solution is unique.
3. The solution is stable, i.e. the solution depends continuously on changes in the data.

There are several different aspects of the weakly supervised object localization problem that can violate these conditions, which would make WSOL an ill-posed problem. First, lets consider the problem in more explicit terms. Suppose that we have the ability to model some posterior distribution $$P(\mathbf{y}|\mathbf{x}; \theta, h)$$ where $$y$$ is the image-level label, $$\mathbf{x} \in \mathbb{R}^{H \times W \times C}$$ is an image, $$\theta$$ is the set of parameters for the classification model $$f(\mathbf{x}; \theta)$$, and $h \in \mathbb{R}^{H \times W \times C}$ is a binary mask that is a function of the model parameters $$\theta$$ and input image $$$x$$ which decomposes the image pixels into a part-whole hierarchy. Following from the example in \[2\], imagine a collection of duck images and the part-whole that might emerge from 

### Inductive Bias with the Equivariant Regularizer

### Affine Transformations 

### Todo

1. Ill-posedness
2. Inductive Bias

## References
1. __[Self-supervised equivariant attention mechanism for weakly supervised semantic segmentation](https://openaccess.thecvf.com/content_CVPR_2020/html/Wang_Self-Supervised_Equivariant_Attention_Mechanism_for_Weakly_Supervised_Semantic_Segmentation_CVPR_2020_paper.html)__. Wang, Yude, et al., Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. __2020__.
2. __[Evaluating weakly supervised object localization methods right](https://openaccess.thecvf.com/content_CVPR_2020/html/Choe_Evaluating_Weakly_Supervised_Object_Localization_Methods_Right_CVPR_2020_paper.html)__". _Choe, Junsuk, et al._ Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. __2020__.
3. __[Scops: Self-supervised co-part segmentation](https://openaccess.thecvf.com/content_CVPR_2019/html/Hung_SCOPS_Self-Supervised_Co-Part_Segmentation_CVPR_2019_paper.html)__. _Hung, Wei-Chih, et al._, Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. __2019__.
4.  __[Unsupervised discovery of object landmarks as structural representations](https://openaccess.thecvf.com/content_cvpr_2018/html/Zhang_Unsupervised_Discovery_of_CVPR_2018_paper.html)__. _Zhang, Yuting, et al._, Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. __2018__.
5.  __[Unsupervised learning of object landmarks by factorized spatial embeddings](https://openaccess.thecvf.com/content_iccv_2017/html/Thewlis_Unsupervised_Learning_of_ICCV_2017_paper.html)__. _Thewlis, James, Hakan Bilen, and Andrea Vedaldi._, Proceedings of the IEEE international conference on computer vision. __2017__.
