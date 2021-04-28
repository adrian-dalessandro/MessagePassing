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

There are several different aspects of the weakly supervised object localization problem that can violate these conditions, which would make WSOL an ill-posed problem. First, lets consider the problem in more explicit terms. Suppose that we have the ability to model some posterior distribution $$P(\mathbf{y}|\mathbf{x}; \theta, h)$$ where $$y$$ is the image-level label, $$\mathbf{x} \in \mathbb{R}^{H \times W \times C}$$ is an image, $$\theta$$ is the set of parameters for the classification model $$f(\mathbf{x}; \theta)$$, and $h \in \mathbb{R}^{H \times W \times C}$ is a binary mask that is a function of the model parameters $$\theta$$ and input image $$$x$$ which decomposes the image pixels into a part-whole hierarchy. Following from the example in \[2\], imagine a collection of animal images and the part-whole hierarchies that explains the semantics of each image. Suppose we want to use these part-whole hierarchies to classify whether an image contains a duck or not. We can imagine a parse tree that first splits the foreground objects (the ducks!) from the background scene (the places where we find ducks!). Then we can imagine the foreground object getting split into things like wings, feet, a beak, eyes, etc. --  the set of all the high-level parts that we understand to comprise a duck. We could break these up further, but this level of granularity is sufficient. Now, imagine the next step in the decomposition of the background. Perhaps the scene is comprised of things like water, certain types of plants, and land. Maybe you will occassionally find the rare duck in a city with some buildings behind it, or concrete beneath it. What we have created is a bunch of foreground and background parts that can be used to determine the presence of ducks. This is where we run into a major problem. For the problem of object localization, we wish to identify and select every part that belongs to the foreground object such that we select the whole foreground object. But suppose that duck feet, a foreground part, occurs significantly less often than water, a background scene part. Perhaps the duck feet are often hidden away under the surface of the water. When considering a model optimized for classification, it's a completely valid option to select water as a discriminating feature and it's a completely valid option to ignore duck feet. If this is the case, then there is no way to localize the relevant foreground object from the class label. A solution does no exist.

### Inductive Bias with the Equivariant Regularizer

### When Do Equivariant Regularizers Work?

### What Affine Transformations Matter?

### Todo

1. Ill-posedness
2. Inductive Bias

## References
1. __[Self-supervised equivariant attention mechanism for weakly supervised semantic segmentation](https://openaccess.thecvf.com/content_CVPR_2020/html/Wang_Self-Supervised_Equivariant_Attention_Mechanism_for_Weakly_Supervised_Semantic_Segmentation_CVPR_2020_paper.html)__. Wang, Yude, et al., Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. __2020__.
2. __[Evaluating weakly supervised object localization methods right](https://openaccess.thecvf.com/content_CVPR_2020/html/Choe_Evaluating_Weakly_Supervised_Object_Localization_Methods_Right_CVPR_2020_paper.html)__". _Choe, Junsuk, et al._ Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. __2020__.
3. __[Scops: Self-supervised co-part segmentation](https://openaccess.thecvf.com/content_CVPR_2019/html/Hung_SCOPS_Self-Supervised_Co-Part_Segmentation_CVPR_2019_paper.html)__. _Hung, Wei-Chih, et al._, Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. __2019__.
4.  __[Unsupervised discovery of object landmarks as structural representations](https://openaccess.thecvf.com/content_cvpr_2018/html/Zhang_Unsupervised_Discovery_of_CVPR_2018_paper.html)__. _Zhang, Yuting, et al._, Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. __2018__.
5.  __[Unsupervised learning of object landmarks by factorized spatial embeddings](https://openaccess.thecvf.com/content_iccv_2017/html/Thewlis_Unsupervised_Learning_of_ICCV_2017_paper.html)__. _Thewlis, James, Hakan Bilen, and Andrea Vedaldi._, Proceedings of the IEEE international conference on computer vision. __2017__.
