---
layout: post
title: "Equivariant Losses & Weakly Supervised Localization"
tagline: "TODO"
author: Adrian D'Alessandro
excerpt_separator: <!--more-->
tags: localization weak supervision
---

Weakly supervised localization is the very challenging task of identifying and grouping the regions of an image that contain some object of interest when the only information you have is that the object of interest is present within the image. Perhaps you have a whole bunch of images of horses and dogs, and you want to figure out exactly which pixels in an image belong to the dogs and which pixels belong the horses -- BUT you only know if an image contains a horse or a dog. You haven't been told where they are. It's an interesting problem!

[//]:  # (Maybe put a picture here?)


## References
1. "__[Self-supervised equivariant attention mechanism for weakly supervised semantic segmentation](https://openaccess.thecvf.com/content_CVPR_2020/html/Wang_Self-Supervised_Equivariant_Attention_Mechanism_for_Weakly_Supervised_Semantic_Segmentation_CVPR_2020_paper.html)__". Wang, Yude, et al., Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. __2020__.
2. "__[Scops: Self-supervised co-part segmentation](https://openaccess.thecvf.com/content_CVPR_2019/html/Hung_SCOPS_Self-Supervised_Co-Part_Segmentation_CVPR_2019_paper.html)__". _Hung, Wei-Chih, et al._, Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. __2019__.
3.  "__[Unsupervised discovery of object landmarks as structural representations](https://openaccess.thecvf.com/content_cvpr_2018/html/Zhang_Unsupervised_Discovery_of_CVPR_2018_paper.html)__". _Zhang, Yuting, et al._, Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. __2018__.
4.  "__[Unsupervised learning of object landmarks by factorized spatial embeddings](https://openaccess.thecvf.com/content_iccv_2017/html/Thewlis_Unsupervised_Learning_of_ICCV_2017_paper.html)__". _Thewlis, James, Hakan Bilen, and Andrea Vedaldi._, Proceedings of the IEEE international conference on computer vision. __2017__.