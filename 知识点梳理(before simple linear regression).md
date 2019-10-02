#####Part1

- 正态分布概率密度函数： $f(x) = \frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{1}{2\sigma^2}(x-\mu)^2}$，记做 $X\sim N(\mu,\sigma^2)$

  标准正态分布概率密度函数：$f(x) = \frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}x^2}$，记做 $X\sim N(0,1)$，用$\phi(x)$表示，分布函数用$\Phi(x)$表示，对应于$Z$统计量

  - 当$X\sim N(\mu,\sigma^2)$，则$\overline{X}\sim N(\mu,\frac{\sigma^2}{n})$，无论n的大小，等价地，$\frac{\overline{X}-\mu}{\sigma/\sqrt{n}}\sim N(0,1)$
  - 从均值为$\mu$，方差为$\sigma^2$的**任意**总体抽取样本量为n的样本，只要n足够大，则$\overline{X}\sim N(\mu,\frac{\sigma^2}{n})$
  - 如果$\sigma^2$未知且总体不服从正态分布，只要n足够大，可用$s$近似代替$\sigma$进行计算

  - 二项分布的正态近似：设随机变量$X\sim B(n,p)$，$\lim_{n\rightarrow\infty}P\{\frac{X-np}{\sqrt{np(1-p)}}\leq x\}=\int_{-\infty}^{x}\frac{1}{\sqrt{2\pi}}e^{-t^2\over 2}dt$

    或者说，二项随机变量$X$近似服从正态分布$N(np,np(1-p))$

    - 样本比例的抽样分布可以用该方法进行处理

- 常用统计量
  1. 样本均值： $\overline{X}=\frac{\sum_{i=1}^{n}X_i}{n}$
  2. 样本方差： $S^2=\frac{\sum_{i=1}^{n}(X_i-\overline{X})^2}{n-1}$
  3. 样本$k$阶矩： $m_k=\frac{\sum_{i=1}^{n}X_i^k}{n}$
  4. 样本$k$阶中心矩：$v_k=\frac{\sum_{i=1}^{n}(X_i-\overline{X})^k}{n-1}$ ($v_2$就是$S^2$)

- $\chi^2$分布：$\sum_{i=1}^{n}X_i^2\sim\chi^2(n)$

  - $E(\chi^2)=n,\;D(\chi^2)=2n$
  - $\chi^2(n_1)+\chi^2(n_2)=\chi^2(n_1+n_2)$
  - 若$X\sim N(\mu,\sigma^2)$，则$\frac{(n-1)S^2}{\sigma^2}\sim \chi^2(n-1)$

- $t$分布：当随机变量$X\sim N(0,1),\;Y\sim \chi^2(n)$，且$X$与$Y$独立，则$\frac{X}{\sqrt{Y/n}}\sim t(n)$

  - $t$分布为偶函数，两侧尾部比$N(0,1)$粗一些，方差大一些

  - $n\geq2$时 $E(t)=0$，$n\geq3$时 $D(t)=\frac{n}{n-2}$

  - 当$X\sim N(\mu,\sigma^2)$，则$\frac{\overline{X}-\mu}{S/\sqrt{n}}\sim t(n-1)$

    如果$\sigma^2$未知且为小样本，则用该式作为检验统计量

  - 当$X\sim N(\mu_1,\sigma^2),\;Y\sim N(\mu_2,\sigma^2)$，$S^2_{xy}=\frac{(n-1)S_x^2+(m-1)S_y^2}{n+m-2}$，则$\frac{(\overline{X}-\overline{Y})-(\mu_1-\mu_2)}{S_{xy}}\sqrt{\frac{mn}{m+n}}\sim t(m+n-2)$

- $F$分布：当$Y,\;Z$分别服从自由度为$m,\;n$的$\chi^2$分布，则$\frac{Y/m}{Z/n} \sim F(m,n)$

  - $n\geq2$ 时$E(F)=\frac{n}{n-2}$，$n\geq4$时 $D(F)=\frac{2n^2(m+n-2)}{m(n-2)(n-4)}$
  - $F_p(v_1,v_2)=\frac{1}{F_{1-p}(v_2,v_1)}$
  - 当$X\sim t(n)$，则$X^2\sim F(1,n)$
  - 当$X\sim N(\mu_1,\sigma^2),\;Y\sim N(\mu_2,\sigma^2)$，则$\frac{S^2_x/S^2_y}{\sigma_1^2/\sigma_2^2}=\frac{S^2_x/\sigma_1^2}{S^2_y/\sigma_2^2}\sim F(n_1-1,n_2-1)$

##### part2

参数估计
- 点估计(point estimate)
- 区间估计(interval estimate)
  - 往往$\overline{X}$是已知的而$\mu$是未知的
  - 可解释为 e.g. 约有95%的样本均值所构造的2个$\sigma$区间会包括$\mu$
  - 置信水平 1-$\alpha$ (confidence level / confidence coeficient)，$\alpha$代表的是右侧(两侧)面积为$\alpha$，$Z$值等统计量可理解为距离中心轴的距离(因为$Z$即$\Phi$，给定$\alpha$后其值就是中心区域剩余面积，越小则说明$\alpha$位置离中心越近)
  - 