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

### 稀疏矩阵

三元组表示法，行、列、元素值





