# fibonacci数列通项公式求解
## 第一种 设等比数列
* $f(n)=f(n-1)+f(n-2)$
* 设$f(n)=q^n$
* 则$q^n=q^{n-1}+q^{n-2}$
* $q^{n-2}.(q^2-q-1)=0$
* 解出 $q$=$\frac{1\pm \sqrt{5}}{2}$
* $f(n)$=$c_1*q_1+c_2*q_2$
*
$$
\begin{align*}
c_1 \cdot \frac{1+\sqrt{5}}{2} &+ c_2 \cdot \frac{1-\sqrt{5}}{2} = 0 \\
c_1 \cdot \left(\frac{1+\sqrt{5}}{2}\right)^2 &+ c_2 \cdot \left(\frac{1-\sqrt{5}}{2}\right)^2 = 0
\end{align*}
$$

* 解出$c_1=\frac{1}{\sqrt{5}},c_2=-\frac{1}{\sqrt{5}}$
* So $f(n)=(\frac{1}{\sqrt{5}})\cdot(\frac{1+\sqrt{5}}{2})^n+(-\frac{1}{\sqrt{5}})\cdot(\frac{1-\sqrt{5}}{2})^n$

## 第二种 线性代数 linear algebra  
*  令
$$
\mathbf{v_n}=
\begin{bmatrix}
v_n \\
v_{n+1}
\end{bmatrix}
$$
* 发现
$$
\mathbf{v_1}=
\begin{bmatrix}
1\\
1
\end{bmatrix}
\quad \mathbf{v_2}=
\begin{bmatrix}
1\\
2
\end{bmatrix}
\quad \mathbf{v_2}=
\begin{bmatrix}
0&&1\\
1&&1
\end{bmatrix}
\cdot \mathbf{v_1}
$$
* Obviously 
$$
\mathbf{v_n}=
\begin{bmatrix}
0&&1\\
1&&1
\end{bmatrix}^n
\cdot
\begin{bmatrix}
1\\
1
\end{bmatrix}
$$ 
* 求矩阵的特征值
$$ det(A-{\lambda I})=
\begin{vmatrix}
-{\lambda}&&1\\
1&&1-{\lambda}
\end{vmatrix}=0 
$$
* 解得$\lambda=\frac{1\pm{\sqrt{5}}}{2}$
* 可以求两个特征向量
$$
A_1=
\begin{bmatrix}
1\\
\frac{1+\sqrt{5}}{2}
\end{bmatrix}
\quad A_2=
\begin{bmatrix}
1\\
\frac{1-\sqrt{5}}{2}
\end{bmatrix} 
\quad A=
\begin{bmatrix}
1&&1\\
\frac{1+\sqrt{5}}{2}&&\frac{1-\sqrt{5}}{2}
\end{bmatrix}=
\begin{bmatrix}
A_1&&A_2

\end{bmatrix}
$$
* 求$A$的Inverse,因为计算量较大，就直接给出结果
$$
A^{-1}=
\begin{bmatrix}
\frac{-1+\sqrt{5}}{2\sqrt{5}}&&\frac{1}{\sqrt{5}}\\
\frac{-1-\sqrt{5}}{2\sqrt{5}}&&-\frac{1}{\sqrt{5}}\\

\end{bmatrix}
$$
* 通过 ${\lambda}$的值可以直接得出伴随矩阵$D$
$$ D=
\begin{bmatrix}
\frac{1+\sqrt{5}}{2}&&0\\
0&&\frac{1-\sqrt{5}}{2}
\end{bmatrix}
$$ 
* 由公式可得
$$
\begin{bmatrix}
0&&1\\
1&&1

\end{bmatrix}^n=
A^{-1} D^n A

$$
* 由矩阵乘法可算，计算比较简单，就不写具体计算过程了
$$
\mathbf{v_n}=
\begin{bmatrix}
1&&1\\
\frac{1+\sqrt{5}}{2}&&\frac{1-\sqrt{5}}{2}
\end{bmatrix}
\begin{bmatrix}
\frac{1}{\sqrt{5}}(\frac{1+\sqrt{5}}{2})^n\\
-\frac{1}{\sqrt{5}}(\frac{1-\sqrt{5}}{2})^n
\end{bmatrix}
$$ 
* So $v_n=(\frac{1}{\sqrt{5}})\cdot(\frac{1+\sqrt{5}}{2})^n+(-\frac{1}{\sqrt{5}})\cdot(\frac{1-\sqrt{5}}{2})^n$
