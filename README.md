## Determinant(行列式)![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Determinant.png)### Cramer's-law(克拉默法则)- 列出系数行列式![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Cramer's-rule.png)- 若上述方程组的系数行列式 D≠0，则方程组存在唯一解 x1=D1/D，x2=D2/D，...，xn=Dn/D，其中Di(i=1,2,..,n)### 常用行列式 - 下三角行列式，主轴元素之积- 上三角行列式，经过 n+(n-1)+...+1=1/2n(n-1)次行变换得到下三角行列式- 对角行列式，主轴元素之积- 副对角线对角行列式，经过 n+(n-1)+...+1=1/2n(n-1) 次行变换得到对焦行列式### 行列式性质- |A|=|AT|- 对换行列式的两行(列)，行列式变号 (对换n次，乘以 (-1^n))- 若行列式有两行(列)完全相同，则此行列式等于零- 行列式某一行(列)中所有的元素都乘同一数k，等于用数k乘此行列式- 行列式某一行(列)的所有元素的公因子可以提到行列式记号的外面- 行列式中如果有两行(列)元素成比例，此行列式等于0- 若行列式的某一行(列)的元素都是两数之和，例如第i行的元素都是两数之和，可将行列式拆开- 把行列式的某一行(列)个元素乘同一数然后加到另一行(列)对应的元素上去，行列式不变### 行列式按行(列)展开- 余子式 Aij = (-1)^i+j Mij，Mij是余子式- 如果其中第i行(列)所有元素除(i,j)元aij外都为零，D=aij*Aij- 行列式等于它的任一行(列)的各元素与其对应的代数余子式乘积之和- D=ai1Ai1 + ai2Ai2 + ... + ainAin 或 D=aj2Aj2 + aj2Aj2 + ... + anjAnj#### 典型例题- 数学归纳法![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Determinant-instance.png)#### 范德蒙的行列式(可用在题目计算中)![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Vandermonde-determinant.png)- 行列式某一行(列)的元素与另一行(列)的对应元素的代数余子式乘积之和等于零- ai1Aj1 + ai2Aj2 + ... + ainAjn =0 或 D=a1iA1j + a2iA2j + ... + aniAnj = 0## (Matrix)矩阵![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Matrix.png)- 实矩阵，元素是实数- 复矩阵，元素是复数- An，n阶方阵- 行矩阵(行向量) A=(a1, a2, ..., an)- 列矩阵(列向量) B=(b1, b2, ..., bm)T- 同型矩阵，行数与列数相等- 相等矩阵，aij = bij，A=B- 零矩阵，O，元素都是零的矩阵- 系数矩阵 A=(aij)- 未知数矩阵 x=(x1, x2, ..., xn)T- 常数项矩阵 b=(b1, b2, ..., bm)T- 增广矩阵 B=A|b#### 典型例题- 凑![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/matrix-instance.png)### 线性变换![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Linear-transformation.png)- 表示一个从变量 x1,x2,...,xn 到变量 y1,y2,...,ym 的线性变换，aij为常数，线性变换的系数aij构成矩阵A=(aij)mxn![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Linear-transformation-corresponding-to-determinant.png)- 对角阵 ∧=diag(λ1, λ2, ..., λn)- 单位矩阵，E=diag(1, 1, ..., 1)### 矩阵的运算#### 矩阵加法- 交换律 A+B=B+A- 结合律 (A+B)+C=A+(B+C)- 负矩阵 A=(aij)，记 -A=(-aij)，A+(-A)=O- 矩阵的减法 A-B=A+(-B)#### 数与矩阵相乘- 与行列式不同，常数只需要提取一次#### 设A、B为 mxn 阶矩阵，λ，u为数- 结合律 (λu)A=λ(uA)- 分配律 (λ+u)A=λA+uA- 分配律 λ(A+B)=λA+λB- 矩阵加法与数乘矩阵统称为矩阵的**线性运算**### 矩阵与矩阵相乘#### 行乘列- 设A=(aij)是一个 mxs 矩阵，B=(bij)是一个 sxn 矩阵，那么规定矩阵A与矩阵B的乘积是一个mxn矩阵C=(cij)- cij=∑aikbkj，记为 C=AB#### 典型例题![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Row-by-column-instance.png)#### 列乘行，算出一个新矩阵- 可交换矩阵，AB=BA- 矩阵 A≠O，矩阵 B≠O，可能 BA=O- 若有两个矩阵，A、B满足AB=O，不能得到 A=O 或 B=O- 若A≠O而A(X-Y)=O，也不能得出X=Y的结论- 结合律，(AB)C=A(BC)- 结合律，λ(AB)=(λA)B=A(λB)- 分配律，A(B+C)=AB+AC，(B+C)A=BA+CA- EA=AE=A#### 矩阵幂- A^1=A，A^2=A^1\*A^1，...，A^(k+1)=A^k\*A^l- 结合律 A^k*A^l=A^(k+l)- (A^k)l=A^(kl)- **矩阵乘法不满足交换律**，(AB)^k≠A^k*B^k- (A+B)^2=A^2 + AB + BA + B^2- (A-B)(A+B)=A^2 + AB - BA - B^2#### 反证法![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Counter-evidence.png)#### 转置- A=(AT)T- (A+B)T = AT + BT- (λA)T = λAT- (AB)T = BTAT **穿脱原则** - 转置的妙用![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Transpose-instance.png)#### 对称矩阵- 如果AT=A，即 aij=aji(i,j=1,2,...,n)，A称为对称矩阵- 元素以对角线为对称轴对应相等#### 方阵行列式- |AT|=|A|- |λA|=λ^n|A|- |AB|=|A||B|- |AB|=|B||A|#### 伴随矩阵- A\*A=|A|E### 逆矩阵- AB=BA=E，说矩阵A是可逆的，把矩阵B称为A的逆矩阵，简称逆阵- 如果矩阵A可逆，**A的逆矩阵唯一**- 若BC都是A的逆矩阵，B=BE=B(AC)=(BA)C=EC=C#### 伴随矩阵和逆矩阵的关系- 若|A|≠0，则矩阵A可逆，且 A^-1=1/|A|\*A\*，A\*为矩阵A的伴随矩阵- A\*A=A\*A=|A|E- 奇异矩阵，|A|=0，否则称非奇异矩阵- A是可逆阵的充分必要条件是|A|≠0，即可逆矩阵是非奇异矩阵- 若AB=E(或 BA=E)，则 B=A^-1- 若A可逆，(A^-1)^-1=A- 若A可逆，数λ≠0，则λA可逆，且(λA)^-1=1/λ\*A^-1- 若A、B为同阶矩阵且均可逆，则AB亦可逆，且 (AB)^-1=(B^-1)(A^-1) **穿脱原则**#### 逆矩阵的初步应用- 矩阵A的m次多项式，A为n阶矩阵，记 φ(A)=a0E+a1A+...+amA^m- φ(A)称为矩阵A的m次多项式- 矩阵A的多项式**可交换**- 如果 A=P∧P^-1，A^k=P(∧^k)P^-1- ∧=diag()为对角矩阵，则 ∧^k=diag(λ1^k, λ2^k,..., λn^k)### 矩阵分块#### 分块矩阵求逆- 主轴对角线上的分块矩阵![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Block-matrix-inversion.png)- 副对角线上的分块矩阵![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Block-matrix-inversion-3.png)- 上三角分块矩阵![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Block-matrix-inversion-1.png)- 下三角分块矩阵![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Block-matrix-inversion-2.png)## 矩阵初等变换与线性方程组![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Matrix-Elementary-Transformation%26Linear-Equations.png)### 矩阵初等行变换- 对换两行(对换i，j两行，记 ri<->rj)- 以数k≠0乘某一行中的所有元- 把某一行所有元的k倍加到另一行对应的元上去- 把上面的行换成列，即初等列变换### 初等行变换的逆变换- 对换两行的逆变换是本身- ri\*k的逆变换ri\*(1/k)- ri+krj 的逆变换 ri+(-k)rj### 等价关系- A与B行等价，矩阵A经有限次初等行变换得到矩阵B- A与B列等价，矩阵A经有限次初等列变换得到矩阵B- A与B等价，矩阵A经过有限次初等变换得到矩阵B，A~B### 等价关系的性质- 反身性 A~A- 对称性 若A~B，则B~A- 传递性 若A~B，B~C，则A~C### 通过行变换化出行阶梯型矩阵- **非零行的首非零元**，竖线右方的第一个元为非零元![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Line-minimalist-matrix.png)#### 行最简形矩阵- 非零行的首非零元为1- 首非零元所在列的其它元均为0#### 标准形- 对最简形矩阵施以初等列变换![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Standard-form.png)- F的左上角是一个单位矩阵、- 对于 mxn 矩阵A，可经过初等变换把它化为标准形![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Standard-form-1.png)- 所有与A等价的矩阵组成一个集合，标准形F是这个集合中形状最简单的矩阵### 初等变换的性质- 设A与B为 mxn 矩阵- A与B行等价，充分必要条件，存在m阶矩阵P使得 PA=B- A与B列等价，充分必要条件，存在n阶矩阵Q使得 AQ=B- A~B，充分必要条件，存在m阶矩阵P和n阶可逆矩阵Q，使得 PAQ=B#### 初等矩阵，由单位矩阵E经过一次初等变换得到的矩阵##### 把单位矩阵中第i，j两行对换 E(i, j)- E(i,j)A，对矩阵A实施初等行变换- AE(i,j)，对矩阵A实施初等列变换 ##### 以数k≠0乘单位矩阵的第i行(第i列)- AE(i(k))，以数k乘A的第i行- E(i(k))A，以数k乘A的第i列##### 以k乘单位矩阵的第j行加到第i行上或以k乘单位矩阵的第i列加到第j列上- E(ij(k))- E(ij(k))A，把A的第j行乘k加到第i行上- AE(ij(k))，把A的第i列乘k加到第j列上#### 初等矩阵逆变换- E(i,j)^-1=E(i,j)- E(i(k))^-1=E(i(1/k))- E(ij(k))^-1=E(ij(-k))#### 典型例题![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Elementary-transformation-instance.png)#### 有限次初等矩阵变换- 方阵A可逆，充分必要条件，存在有限个初等矩阵P1，P2，...，Pl，使得A=P1P2...Pl- 方阵A可逆，充分必要条件，A与E行等价#### 初等行变换求逆矩阵(重点!!!!)- 存在可逆矩阵P，使PA=B，PE=P- P(A,E)=(B,P)，<=> (A,E) 行等价 于 (B,P)- 对矩阵(A,E)作初等行变换，把A变为B时，E就变为P- 一般化为最简形矩阵#### 典型例题- 非齐次线性方程组，Ax=b，求x- 由题知，Ax=b，AE=A，拼增广矩阵 (A, b) 作初等变换为(E,x）### 矩阵的秩- **矩阵的k阶子式**，在 mxn 矩阵A中，任取 k行 与 k列，位于行列交叉处的k^2个元素- mxn 矩阵A的k阶子式共有 C(k m) * C(k n)- 设 A 行等价 B，则A与B中非零子式的最高阶数相等#### 最高阶非零子式- 在矩阵A中有一个不等于0的r阶子式D，且所有r+1阶子式全为0- 称以上的矩阵A为最高阶非零子式，数r称为矩阵A的秩，R(A)- 零矩阵的秩等于00- 若矩阵A中有某个s阶子式不为0，则R(A)>=s- 若A中所有t阶子式全为0，则R(A)<t- 若A为 mxn 矩阵，则 0≤R(A)≤min{m, n}- R(AT)=R(A)#### 行列式与秩的关系- 由于A的n阶子式只有一个 |A|，故当 |A|≠0时，R(A)=n- 当 |A|=0时，R(A)<n- 可逆矩阵的秩等于矩阵的阶数，不可逆矩阵的秩序- 可逆矩阵又称**满秩矩阵**，不可逆矩阵(奇异矩阵)，又称**降秩矩阵**- 若A~B，R(A)=R(B)- 根据A~B，充分必要条件，存在可逆矩阵P、Q，使得PAQ=B，R(A)=R(B)#### 秩的基本性质- 0 ≤ R(Amxn) ≤ min{m, n}- R(AT)=R(A)- 若A~B，则R(A)=R(B)- 若P、Q可逆，则 R(PAQ)=R(A) #### 秩的基本性质- **增广**矩阵的秩- 增广矩阵的秩**大于等于**系数矩阵的秩- max{R(A), R(B)} ≤ R(A, B) ≤ R(A) + R(B)，因为A的最高阶非零子式总是(A, B)的非零子式- 当 B=b 为非零列向量时，有 R(A) ≤ R(A, b) ≤ R(A)+1- 矩阵**和**的秩- R(A+B) ≤ R(A)+R(B)- 矩阵**乘积**的秩- R(AB) ≤ min{R(A), R(B)}#### 典型例题![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Rank-properties-instance.png)- 矩阵**乘积为零**的秩- 若 A(mxn)B(nxl) = O，则 R(A) + R(B) ≤ n- **列满秩矩阵**，矩阵A的秩等于它的**列数**；当A为**方阵**时，列满秩矩阵就成为**满秩矩阵**，即**可逆矩阵**- 设 AB=O，若A为列满秩矩阵，则B=O，(R(AB) ≤ min{R(A), R(B)}， R(B)=0，故B=O)- 这以结论通常称为矩阵乘法的消去律### 典型例题![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/The-nature-of-rank-instance.png)![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/The-nature-of-rank-instance-2.png)- **抽象类**题目，全部用性质解![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/The-nature-of-rank-instance-1.png)- 列乘行 R(AB)≤min{R(A), R(B)}![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Matrix-multiplication-instance.png)### 线性方程组的解- 线性方程组有解，称**相容**- 线性方程组无解，称**不相容**#### n元线性非齐次方程组Ax=b解的充要条件- 无解的充分必要条件是 R(A)<R(A, b)- 有惟一解的充分必要条件是 R(A)=R(A, b)=n- 有无限多解的充分必要条件是 R(A)=R(A, b)<n#### 解方程组- 写出系数矩阵，化为行最简形矩阵- 将非零行方程写出，找出共有的元，如果有，分别设为常数(基础解系的话分别设为1，其他为0)，写出解- 注意，b是**常数项**！#### 线性方程组解的定理- n元齐次线性方程组 Ax=0 有非零解的 充分必要条件 R(A)<n- 非齐次线性方程组 Ax=b (b一维列向量)有解的 **充分必要条件** R(A)=R(A, b)- 非齐次线性方程组 AX=B (B矩阵)有解的 **充分必要条件** R(A)=R(A, B)- 设AB=C，则R(C)≤min{R(A), R(B)}## Linear-correlation-of-vector-groups(向量组的线性相关性)![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Linear-correlation-of-vector-groups.png)### 向量组及其线性组合- **n维向量**，n个有次序的数a1, a2, ..., an所组成的数组- 这n个数称为该向量的n个分量，第i个数ai称为第i个分量- **实向量**，分量全为实数的的向量- **复向量**，分量为复数的向量- **向量组**，若干个同维数的列向量所组成的集合- **线性组合**，给定向量组A:a1, a2, ..., am，对于任何一组实数k1,k2,...,km- 表达式 k1a1 + k2a2 + ... + kmam，向量组A的一个**线性组合**，k1，k2，...，km称为这个线性组合的系数- b = λ1a1 + λ2a2 + ... + λmam，向量b是向量组A的**线性组合**，向量b能由向量组A**线性表示**- 向量 b 能由向量组A线性表示，方程组 x1a1 + x2a2 + ... + xmam = b **有解**#### 线性表示的相关定理- 向量b能由向量组A:a1,a2,...,am**线性表示**的充分必要条件是矩阵A=(a1,a2,...,am)的**秩等于**矩阵B=(a1,a2,...,am,b)的**秩**- **向量组等价**，向量组A与向量组B能**相互线性表示**-  向量B:b1, b2,...,bl能由向量组A:a1,a2,...,am**线性表示**的充分必要条件是矩阵A=(a1,a2,...,am)的**秩等于**矩阵(A,B)=(a1,a2,...,am,b1,...,bl)的**秩**，即R(A)=R(A,B)- 向量组A:a1,a2,...,am，能由向量B:b1, b2,...,bl等价的充分必要条件是R(A)=R(B)=R(A, B)#### 典型例题![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Linear-representation.png)![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Linear-representation-1.png)-  向量B:b1, b2,...,bl能由向量组A:a1,a2,...,am**线性表示**，R(A)=R(A, B)，而R(B)≤R(A, B)，则R(b1, b2, ..., bl)≤R(a1, a2, ..., am)- 向量组B能由向量组A线性表示 <=> 有矩阵K，使 B=AK；方程 AX=B 有解#### A能由B线性表示的必要条件 R(A)≥R(B)#### A能由B线性表示的充要条件 R(A)=R(A,B)- 单位坐标向量，n阶单位矩阵E=(e1, e2, ..., en)的列向量### 向量组线性相关性#### 线性相关定义- 给定向量组A: a1, a2, ..., am- 如果存在不全为0的数k1,k2,...,km使得 k1a1 + k2a2 + ... + kmam = 0，称向量组A线性相关，否则称它线性无关- a1能由 a2,...,am线性表示，则 a1,a2, ..., am 线性表示#### 典型例题- 线性无关的定义![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Linear-independent-definition.png)![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Linearly-independent-instance.png)![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Linear-correlation-instance.png)![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Linear-correlation-instance-1.png)![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Linear-correlation-definition-instance.png)#### 线性相关矩阵的秩与向量个数的关系- 从方程组的角度看，向量组A线性相关，即齐次线性方程组 x1a1 + x2a2 + ... + xmam=0，即Ax=0有非零解- 向量组A:a1, a2, ..., am线性相关的充分必要条件是它所构成的矩阵(相当于方程组的系数矩阵)A=(a1, a2, ..., am)的**秩小于向量个数m**- 向量组A**线性无关**的充分必要条件是 **R(A)=m**#### 典型题目- B=AK- AX=B#### 典型例题(利用线性相关定义反证)![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Linear-correlation-instance.png)#### 简单结论- 若向量组A:a1,a2,...,am线性相关，则向量组B:a1,a2,...,am,am+1 也线性相关- 反之，若向量组B线性无关，则向量组A也线性无关- 数量小的线性相关，数量大的线性相关；数量大的线性无关，数量小的线性无关- m个n维向量组成的向量组，当维数小于向量个数m时，一定线性相关，- **行数小于列数**时一定线性相关- n+1个n维向量一定线性相关- 设向量组：A:a1, a2, ..., am 线性无关，而向量组B:a1, ..., am, b线性相关，则**向量b必能由向量组A线性表示**，且**表示式惟一**### 向量组的秩- 设有向量组A，如果在A中能选出r个向量a1,a2,...,ar，满足- 向量组A0:a1,a2,...,ar 线性无关- 向量组A中任意r+1个向量都线性相关，称向量组A0是A的一个最大线性无关向量组(最大无关组)- 最大无关组所含向量个数r称为向量组A的秩#### 最大无关组等价定义：设向量组A0:a1,a2,...,ar是向量组A的一个部分组，且满足- 向量组A0线性相关- 向量组A的任一向量都能**由向量组A0线性表示**，那么向量组A0便是向量组A的一个**最大无关组**#### 基础解系是解向量组的最大线性无关组- 矩阵的秩等于它的列向量组的秩，也等于它的行向量组的秩- **最大线性无关组**，是行阶梯形矩阵，**非零行的首非零元所在的列向量**- 最简形矩阵与行阶梯矩阵同解，可化成**最简形矩阵**，**求线性表示**- 向量组b1，b2，...，bl能由向量组a1，a2，...，am线性表示的充分必要条件是 R(a1,a2,...,am)=R(a1,...,am,b1,...,bm)- 若向量B能由向量组A线性表示，则 RB ≤ RA### 线性方程组解的结构- n个未知数的齐次线性方程组，Ax=0 有非零解的充分必要条件是 系数矩阵的秩 R(A)<n- n个未知数的非齐次线性方程组 Ax=b 有解的充分必要条件是 R(A)=R(A, b)- 且当R(A)=R(A, b)=n时，方程组有惟一解，当R(A)=R(B)=r<n时有无限多个解- 非齐次线性方程有n+1个**线性无关**的解，则从第二项开始逐个与第一项做差，有n个线性无关的齐次线性方程的解### 向量解的性质- 若x=ξ1，x=ξ2，为向量方程的解，则 x=(ξ1 + ξ2)也是向量方程的解- 若x=ξ1为向量方程的解，k为实数，则x=kξ1也是向量方程的解- 基础解系，x=k1ξ1 + k2ξ2 + ... + ktξt (k1, k2, ..., kt为任意实数)- 设 mxn 矩阵A的秩R(A)=r，则n元齐次线性方程组Ax=0的解集S的秩 Rs=n-r(基础解系的个数 或者 解空间的基的个数)#### 典型例题![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Solution-space-instance.png)- 当R(A)=n时，方程只有零解，没有基础解系#### 典型例题![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Number-of-solutions.png)![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Properties-of-vector-solutions.png)#### 用同解证明秩相同- Ax=0与Bx=0同解，证明R(A)=R(B)- R(ATA)=R)(A)- 设x=η1以及x=η2都是向量方程的解，则x=η1-η2为对应的齐次线性方程 Ax=0 的解- 设x=η是方程的解，x=ξ是方程的解，则x=ξ+η是方程的解- 通解：基础解系 + 特解，x=k1ξ1 + ... + kn-rξn-r + η*### 向量空间- 向量空间，设V为n维向量的集合，如果集合V非空，且集合V对于向量的加法及数乘两种**运算封闭**，那么称集合V为向量空间- 设有向量空间V1及V2，若V1⊆V2，称V1是V2的子空间#### 基，维数，r维向量空间- 设V为向量空间，如果r个向量a1,a2,...,ar∈，且满足- a1,a2,...,ar**线性无关**，V中任一向量都可由a1，a2，...，ar线性表示- 向量组a1,a2,...,ar称为向量空间V的一个基，r称为向量空间V的维数，V为r维向量空间### 坐标- 向量空间V取定一个基a1,a2,...,ar，V中任一向量x可惟一地表示为 x = λ1a1 + λ2a2 + ... + λrar- 数组 λ1，λ2，...，λr称为向量x在基a1,a2,...,ar中的坐标### 自然基- 在n维向量空间中取单位坐标向量组e1,e2,...,en为基，x=x1e1 + x2e2 + ... + xnen- 向量在基e1,e2,...,en中的坐标就是该向量的分量，e1,e2,...,en叫做R^n中的自然基### 基变换公式- 在R^3中取定一个基a1,a2,a3，再取一个新基b1,b2,b3，设A=(a1, a2, a3)，B=(b1, b2, b3)- 基变换公式: 用 a1,a2,a3 表示 b1,b2,b3 的表示式- (坐标变换公式)向量在两个基中的坐标之间的关系式- (a1, a2, a3)=(e1, e2, e3)A，(e1, e2, e3)=(a1, a2, a3)A^-1- (b1, b2, b3)=(e1, e2, e3)B=(a1, a2, a3)(A^-1)B### 过渡矩阵- (b1, b2, b3)=(a1, a2, a3)P，P称为从旧基到新基的**过渡矩阵**### 坐标变换公式- 设向量x在旧基和新基中国的坐标分别为 y1,y2,y3和z1,z2,z3，即 x=(a1, a2, a3)(y1, y2, y3)T，x=(b1, b2, b3)(z1, z2, z3)- A(y1, y2, y3)T = B(z1, z2, z3)，得 (z1, z2, z3)T=(B^-1)A(y1, y2, y3)- (z1, z2, z3)T=P(y1, y2, y3)，是从旧坐标到新坐标得坐标变换公式#### 典型例题![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Base-transformation-formula&coordinate-transformation-formula.png)![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Transition-matrix.png)## Similar-matrix-uadratic-form![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Similar-matrix-quadratic-form.png)### 向量内积、长度及正交性#### 内积(数量积)- 设有n维向量，x=(x1, x2, ..., xn)T，y=(y1, y2, ..., yn)- [x, y]=x1y1 + x2y2 + ... + xnyn- [x, y]=xTy#### 内积性质- 交换律 [x, y]=[y, x]- [λx, y]=λ[x, y]- 分配律 [x+y, z]=[x, z] + [y, z]- 当x=0时，[x, x]=0；当x≠0时，[x, x]>0#### 施瓦茨不等式- ([x, y])^2 ≤ [x, x][y, y]#### n维向量的长度和夹角- ||x||=([x, x])^1/2=(x1^2 + x2^2 + ... + xn^2)^1/2，||x||称为n维向量x的长度(或范数)- 非负性，当x≠0，||x||>0；当x=0时，||x||=0- 齐次性 ||λx||=|λ| ||x||- 当||x||=1，称x为单位向量，若a≠0，取x=a/||a||，则x是一个单位向量- 由施瓦茨不等式，有 -1 ≤ [x, y]/(||x|| ||y||) ≤ 1 (当 ||x|| ||y|| ≠ 0)- 当x≠0，y≠0，θ=arccos [x, y]/(||x|| ||y||)，称为**n维向量的x与y的夹角**- 当[x, y]=0时，称向量x与y正交；若x=0，则x与任何向量都正交#### 正交向量组- 若n维向量a1, a2, ..., ar是一组**两两正交**的**非零向量**，这组向量就是正交向量组- 正交向量组，a1, a2, ..., ar**线性无关**![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Orthogonal-vector-group.png)#### 标准正交基- 设n维向量e1, e2, ..., er 是向量空间V的一个基，如果e1, ..., er两两正交，且都是单位向量，则称e1, ..., er是V的一个标准正交基#### 基标准正交化- 找一组两两正交的单位向量e1,...,er，使得 e1,...,er 与 a1,...,ar等价#### 施密特正交化- b1 = a1- b2 = a2 - ([b1, a2]/[b1, b1])b1- b3 = a3 - ([b1, a3]/[b1, b1])b1 - ([b2, a3]/[b2, b2])b2......- e1 = (1/||b1||)b1, e2=(1/||b2||)b2,......#### 正交矩阵- ATA=E，即A^-1=AT，称A为正交矩阵- n阶正交矩阵A的n个列(行)向量构成向量空间R^的一个**标准正交基**- 方阵A为正交矩阵 充分必要条件 A的**列向量都是单位向量**- 若A和B都是正交矩阵，则AB也是正交矩阵#### 正交变换- 若P为正交矩阵，则线性变换y=Px称为正交变换- 设 y=Px 为正交变换，则有 ||y||=(yTy)^1/2=(xTPTPx)^1/2=(xTx)^1/2=||x||- 由于 ||x|| 表示向量的长度，相当于线段的长度，||y||=||x||说明经正交变换线段长度不变### 方阵的特征值与特征向量#### 方阵特征值/特征向量定义- 设A是n阶矩阵，如果数	λ和n维非零列向量x使关系式， Ax=λx成立- 数λ称为**特征值**，非零向量x称为A对应特征值的**特征向量**#### 特征方程- (A-λE)x=0，有非零解的 充分必要条件 |A-λE|=0- |A-λE|是λ的n次多项式#### 特征值性质- 设n阶矩阵A=(aij)的特征值为 λ1, λ2, ...,λn，- λ1 + λ2 + ... + λn = a11 + a22 + ... + ann- λ1λ2...λn=|A|- 上式推出**可逆矩阵**的 充分必要条件 **n个特征值全不为零**- 设λ=λi为矩阵A的一个特征值，则由方程 (A-λiE)x=0，可求得非零解x=pi，pi是A对应于特征值λi的特征向量(若λi为实数，则pi可取实向量；若λi为复数，则pi为复向量)- λ^2是A^2的特征值，推广，λ^k是A^k的特征值- 当A可逆时，1/λ是A^-1的特征值- **φ(λ)是φ(A)** 的特征值，即矩阵A的多项式的特征值是对应的λ的多项式##### 特征向量线性无关- 设λ1,λ2,...,λm是方阵A的m个特征值，p1,p2,...,pm依次是与之对应的特征向量，如果λ1,λ2,...,λ**m各不相等**，则p1,p2,...,pm**线性无关**- 设λ1和λ2是方阵A的两不同特征值，ξ1, ξ2,..., ξs 和 η1, η2, ..., ηt 分别是对应于λ1和λ2的 线性无关的特征向量，则 ξ1, ξ2,..., ξs, η1, η2, ..., ηt 线性无关- 即 对应于两个**不同特征值**的**线性无关的特征向量组**，**合起来**是线性无关的#### 典型例题![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Eigenvalues-instance.png)- 由题知，P^-1AP可化为特征值为 1 1 0 的对角阵，Q^-1AQ也可以将A化为相同的对角阵，Q=()^T- 根据特征值的定义， Aβ1=β1，Aβ2=β2，Aβ3=0，经验证，只有C选择符合题意### 相似矩阵- 设A、B都是n阶矩阵，若有可逆矩阵P，使 P^-1AP=B，称B是A的**相似矩阵**- 对A进行P^-1AP运算称为对A的**相似变换**，可逆矩阵P称为把A变成B的**相似变换矩阵**#### 典型例题- 相似变换求特征值![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Similarity-transformation-instance.png)#### 相似，特征多项式相同- 设n阶矩阵A与B**相似**，则A与B的**特征多项式相同**，从而A与B的**特征值亦相同**- 若n阶矩阵A与对角矩阵 ∧=diag(λ1, λ2, ..., λn)相似，则 λ1，λ2，...,λn即是A的n个特征值#### 把矩阵A对角化- 对n阶矩阵A，寻求相似变换矩阵P，使P^-1AP=∧，叫做把矩阵A对角化![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Matrix-diagonalization.png)- 由上图知，n阶矩阵A与对角矩阵相似(A能对角化)的充分必要条件是A有n个线性无关的特征向量- **本质上是P可逆**，**|P|≠0**，即P是一个**最大线性无关组**，构成矩阵P的**n个列向量必须线性无关**- 由定义知，P是由n个A的特征向量作为列向量构成的矩阵，则矩阵A的特征值对应的**n个特征向量**线性无关- 如果n阶矩阵A的**n个特征值互不相等**，则A与对角矩阵相似- 当A的特征方程**有重根**，**不一定**有n个线性无关的特征向量，从而**不一定**能对角化#### 垂直(内积为0)只是线性无关中的一种情况，对应分量不成比例### 对阵矩阵的对角化#### 一个n阶矩阵具备什么条件才能对角化，很复杂，仅讨论当A为对称矩阵的情形- 对称矩阵的特征值为实数- 设λ1, λ2是对称矩阵A的两个特征值，p1, p2是对应的**特征向量**，若λ1≠λ2，则p1与p2**正交**- 上面这句话，前提是矩阵A是**对称矩阵**，**p1与p2正交**，就是**垂直**情况，是线性无关中的**一种情况**- 设A为n阶**对称矩阵**，则必有正交矩阵P，使**P^-1AP=PTAP=∧**，其中∧是以A的n个特征值为对角元的对角矩阵- 设A为n阶对称矩阵，λ是A的特征方程的k重根，则矩阵A-λE的秩R(A-λE)=n-k，从而对应特征值λ恰有k个线性无关的特征向量![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Symmetric-matrix-diagonalization.png)#### 典型例题![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Symmetric-matrix-diagonalization-example.png)### 二次型及其标准形#### 标准形(法式)- f=k1y^2 + k2y2^2 + ... + kny^2，只含平方项的二次型#### 规范形- 标准形系数k1,k1,...,kn只在1,-1,0三个数中取值，称为规范形- 当aij为复数，f称为复二次型，当aij为实数，f称为实二次型- f=xTAx，A称为二次型f的矩阵，f叫做对称矩阵A的二次型，R(A)叫做#### 可逆变换- 记C=(cij)，把可逆变换记作 x=Cy，f=xTAx=(Cy)TACy=yT(CTAC)y#### 合同- 设A和B是n阶矩阵，若有可逆矩阵C，使B=CTAC，则称矩阵A与B合同- 若A为**对称矩阵**，则B=CTAC也为对称矩阵，且R(B)=R(A)- BT=(CTAC)T=CTATC=CTAC=B 穿脱原则- 矩阵合同的充要条件：矩阵A，B均为实对称矩阵，则AB二次型xTAx与xTBx相等的正负惯性指数，有相同标准形#### 对称矩阵合同对角化- 使二次型经可逆变换 x=Cy 变成**标准形**，即寻求可逆矩阵B，使CTAC成为**对角矩阵**#### 正交变换化标准形- 任给对称矩阵A，总有正交矩阵P，使 **P^-1AP=∧**，即 **PTAP=∧**- 任给二次型f=∑aixixj，总有正交变换 x=Py，使f化为标准形 f=λ1y1^2 + λ1y2^2 + ... + λ1yn^2- 其中λ1,λ2,...,λn是f的矩阵A=(aij)的特征值#### 二次型与二次曲面![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Quadratic&quadric.png)#### 可逆变换化规范形- 任给n元二次型f(x)=xTAx(AT=A)，总有可逆变换x=Cz，使f(Cz)为规范形### 用配方法化二次型成标准形#### 典型例题- 含有平方项![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Matching-method.png)- 不含平方项，制造平方项![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Matching-method-1.png)### 正定二次型- 正(负)惯性指数，二次型的标准形中正系数的个数称为二次型的正惯性指数，负系数的个数负惯性指数#### n元二次型f=xTaAx为正定的充分必要条件- 它的标准形的n个系数全为正- 它的规范形的n个系数全为1- 它的正惯性指数等于n#### 对称阵正定的充分必要条件- 系数矩阵A的特征值全为正- 系数矩阵A的各阶主子式都为正(赫尔维茨定理)#### 对称矩阵负定充分必要条件- 系数矩阵奇数阶主子式为负，而偶数阶主子式为正 (赫尔维茨定理)#### 典型例题![image](https://github.com/YC-L/Postgraduate-examination/blob/Linear-Algebra/imgs/Positive-instance.png)