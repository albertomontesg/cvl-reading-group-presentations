## FoveaNet: Perspective-aware Urban Scene Parsing
<span style="font-size:30px"> Xin Li, Zequn Jie, Wei Wang, Changsong Liu, Jimei Yang, Xiaohui Shen, Zhe Lin, Qiang Chen, Shuicheng Yan, Jiashi Fen</span>

---

## Self-Driving Car

![Self-Driving Cars](assets/self-driving.gif)

---

# Problem

![Problem](assets/problem_1.png)

+++

![Problem](assets/problem_2.png)
![Problem](assets/problem_3.png)

+++

## Intuition

|||
| ---- | ---- |
|![](assets/problem_image.png) | ![](assets/problem_table.png) |


---

# Solution

*undo* Camara Perspective Projection by

**scale normalization**

---

# FoveaNet

![FoveaNet](assets/foveanet.png)

FCN in FoveaNet: **ResNet-101**

---

### Perspective Estimation Network

![PEN](assets/pen.png)

+++

#### Training

$m$: object in the $n$-th image; $i$: pixel index;

$l(m)$: category label of instance $m$

`$$H_i^{(n)} = \frac{AveSize(l(m))}{Size(m)}$$`

`$$G_i = \frac{1}{N}\sum_{n=1}^N H_i^{(n)}$$`

`$$V_i^{(n)} = H_i^{(n)} + \delta \times G_i$$`

+++

#### Training Samples

![PEN Training](assets/pen_training.png)

---

### Perspective-aware Scene Parsing

<div style="width:70%;margin:auto">
![Parsing Network](assets/parsing_network.png)
</div>

ResNet-101 with shared parameters from `conv1` to `res3_3b3`.

---

### Perspective-aware CRFs

![CRF](assets/crf.png)

+++

`$$\mathcal{E}(l) = \sum_i \psi_u(l_i) + \sum_{i,j} \psi_{p,persp}(l_i, l_j)$$`


`$$\psi_{p,persp}(l_i, l_j) = \mu(p_i, p_j) \nu(l_i, l_j) \kappa(f_i, f_j)$$`

`$$\mu(p_i, p_j) = d_k(\frac{\sum_{m \in \hat{V}} \nu_m}{|\hat{V}|} / \frac{\sum_{n \in B_k} \nu_n}{|B_k|})$$`

---

# Results

Two datasets: **Cityscapes** & **Camvid**

+++

## Results

![Results Table](assets/results_table.png)

+++

![Results](assets/results_1.png)

+++

![Results](assets/results_2.png)

+++

## Results on Cityscapes

![Results Cityscapes](assets/results_cityscapes.png)

+++

## Results on Camvid

![Results Camvid](assets/results_camvid.png)

---

# The END
