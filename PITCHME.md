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

$m$: object in the $n$-th image; $i$: pixel index; $l(m)$: category label of instance $m$

$$H_i^{(n)} = \frac{AveSize(l(m))}{Size(m)}$$

