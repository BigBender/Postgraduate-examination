## 矩阵压缩存储

### 矩阵相加

```cpp

void trsmat(int A[][maxSize], int B[][maxSize], int m, int n){
	for(int i = 0; i < m; i++){
		for(int j = 0; j < n; j++){
			B[j][i] = A[i][j];
		}
	}
}

```
### 矩阵相加

```cpp

void addmat(int C[][maxSize], int A[][maxSize], int B[][maxSize], int m, int n){
	for(int j = 0; i < m; ++i){
		for(int j = 0; j < n; ++j){
			c[i][j] = A[i][j] + B[i][j];
		}		
	}
}

```

### 矩阵相乘

```cpp

void mutmat(int C[][maxSize], int A[][maxSize], int B[][maxSize], int m, int n, int k){
	for(int i = 0; i < m; ++i){
		for(int j = 0; j < k; ++j){
			c[i][j] = 0;
			for(int h = 0; h < n; ++h){
				c[i][j] += A[i][h]*B[h][j];
			}
		}
	}
}

```

### 特殊矩阵

#### 对称矩阵

- 主对角线上下方元素对称相等，相同元素只需要保存一份，只需要存储 n*(n+1)/2

- k=i(i-1)/2+(j-1)，当 i>=j时(下三角区和主对角线)；j(j-1)/2+(i-1)，当i<j(上三角区)

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Symmetric-matrix-compression-storage.png)

#### 三角矩阵

- 只需要存储 n*(n+1)/2 + 1 个元素即可(相比对称矩阵，多出来的那个元素是c)

#### 上三角阵

- 下三角部分(不包括主对角线部分)元素全为c

- 在一维数组存放的下标 
- k = i(i-1)/2+(j-1)，当 i>=j(下三角区和主对角线)；n(n+1)/2，当 i<j(上三角区)

#### 下三角阵

- 上三角部分(不包括主对角线部分)元素全为c

- k = (i-1)(2n-i+2)/2+(j-i)，当 i>=j(上三角区和主对角线)；n(n+1)/2，当 i<j(下三角区)

#### 对角矩阵

- 三对角矩阵

- 当且仅当 |i - j| > 1时，有M(i, j)=0，在一维数组存放的下标 k = 2i + j - 3

- 五对角矩阵

- 当且仅当 |i - j| > 2时，有M(i, j)=0，在一维数组存放的下标 k = 4i + j - 5

#### 对角矩阵（N*N）的压缩存储

- 假设为m（m为奇数）对角

- 将所有的非零元素都存储到一维数组中，分别用按行优先排列和按对角线的顺序排列时,对应的（i,j）（N*N中元素的下标）和k（一维数组中的下标）的关系具体是什么

- **k=(i-1)(m-1)+j-1**
</br>(其中N*N矩阵下标从1开始,压缩矩阵下标从0开始)

### 稀疏矩阵

-  设矩阵A中有**s个非零元素**，且s**远远小于矩阵元素的总数**（即s≦m×n），这s个元素**分布没有规律**

#### 稀疏因子

- 有s个非零元素，令 e=s/(m*n)，称e为矩阵的稀疏因子

- 通常认为 e≤0.05 时称之为稀疏矩阵

- 三元组表示法，行、列、元素值，(i,j,aij)

- 系数矩阵一般的压缩存储方法是三元组和十字链表

#### 三元组顺序表

```cpp

#define MAXSIZE 10000

typedef int datatype

struct triple{
   int   i,j;
   datatype v;
}

struct tripletable{
	triple  data[MAXSIZE];
	int  m,n,t;
}tripletable

```
#### 矩阵转置

- 矩阵的转置

- 一个m×n的矩阵A，它的转置B是一个n×m的矩阵，且a[i][j]=b[j][i]，0≦i≦m，0≦j≦n，即A的行是B的列，A的列是B的行。

- 对三元组M进行转置换，得到三元组T

- 矩阵转置时间复杂度O(n^3)

- 基本思想

- 对 M.data从头至尾扫描：

- 第一次扫描时，将M.data中列号为1的三元组赋值到T.data中

- 第二次扫描时，将M.data中列号为2的三元组赋值到T.data中

- 依此类推，直至将M.data所有三元组赋值到T.data中

```cpp

TransposeSMatrix(M, T) {   
	T.mu=M.nu;  T.nu=M.mu;  T.tu=M.tu;
	if (T.tu)  {     
		q=0； // q为当前三元组在T.data[ ]存储位置(下标)     
		for (col=1; col<=M.nu;  ++col){      
			for (p=0;  p<=M.tu-1;  ++p){ //p为扫描M.data[ ]的“指示器”
	        	if (M.data[p].j= =col){          
	 				T.data[q].i =M.data[p].j;
					T.data[q].j=M.data[p].i;          
					T.data[q].e=M.data[p].e; ++q;
				}  
			}  
		}
	}
}//  TransposeSMtrix

```
#### 快速转置




