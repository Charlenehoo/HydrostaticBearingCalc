# HydrostaticBearingCalc

对于油腔半径，油垫半径依次为$R_0$，$R_1$的圆形油垫来说，其有效面积为：
$$
A_e 
= \frac {
    \pi \left( {R_1}^2 - {R_0}^2 \right)
}{
    2 \ln \frac{R_1}{R_0}
}
$$
设$R_{A_e}$为计算有效面积时的等效半径，使
$
\pi {R_{A_e}}^2 = A_e
$
，则：
$$
R_{A_e}
= \sqrt[]{
    \frac {
        {R_1}^2 - {R_0}^2
    }{
        2 \ln \frac{R_1}{R_0}
    }
} 
= \sqrt[]{
    \frac {R_1 + R_0}{2}
    \cdot \frac {R_1 - R_0}{\ln R_1 - \ln R_0}    
}     
= G \left( 
    A \left( R_1, R_0 \right), 
    L \left( R_1, R_0 \right) 
\right)
$$
推广到油垫小径，油腔小径，油腔大径，油垫大径依次为$R_1$，$R_2$，$R_3$，$R_4$的扇形油垫，
其有效面积是半径依次为
$
R_{A_e1} = G \left( 
    A \left( R_2, R_1 \right), 
    L \left( R_2, R_1 \right) 
\right)
$
以及
$
R_{A_e2} = G \left( 
    A \left( R_4, R_3 \right), 
    L \left( R_4, R_3 \right) 
\right)
$
的圆弧及其两直边中线围出的图形面积；

<img src="images/扇环油垫.jpg" alt="扇环油垫" width="40%" height="auto">


*图1：这是图片的描述。*

对于一个$N$垫，直边封油面宽$B_1$，回油槽宽$B_2$的扇形油垫来说，该面积
$$
A_e 
= \frac {\pi {R_{A_e2}}^2 - \pi {R_{A_e1}}^2}{N}
- 2 \int\limits_{0}^{B} \left( \sqrt[]{{R_{A_e2}}^2 - x^2} - \sqrt[]{{R_{A_e1}}^2 - x^2} \right) dx
$$
其中：
$$
B = \frac {B_1 + B_2}{2} = A \left( B_1, B_2 \right)
$$
注意到：
$$
\begin{aligned}
    &\hspace{1em} \int_{0}^{B} \sqrt[]{R^2 - x^2} dx \\
    &= R^2 \int_{0}^{\sin^{-1} \frac{B}{R}} \cos^2 \theta d\theta \\
    &= R^2 \int_{0}^{\sin^{-1} \frac{B}{R}} \frac{1 + \cos 2 \theta}{2} d\theta \\
    &= R^2 {\left[ \frac {\theta}{2} + \frac {\sin 2 \theta}{4} \right]}_{0}^{\sin^{-1} \frac{B}{R}} \\
    &= \frac{R^2}{2} \sin^{-1} \frac {B}{R} + \frac {B}{2} \sqrt[]{R^2 - B^2}
\end{aligned}
$$
因此，扇形油垫的有效面积为：
$$
A_e = S \left( R_{A_e2} \right) - S \left( R_{A_e1} \right)
$$
其中：
$$
S \left( R \right) = \frac {\pi R^2}{N} 
- R^2 \sin^{-1} \frac {B}{R}
- B \sqrt[]{R^2 - B^2}
$$