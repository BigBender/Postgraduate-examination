## 折半插入排序

与直接插入排序思想类似，区别是查找插入位置的方法不同，折半插入排序是采用折半查找法查找插入位置的。

将待排序的记录R[i]，通过折半查找的方式在有序序列中查找插入位置。

### 示例

对序列：**13，38，49，65，76，97，27，49**进行一趟折半插入排序。

前6个元素已经排好序列，查找27的插入位置

1. mid = (0 + 5)/2 = 2，当前位置，27 < 49，27的插入位置在49的低半区
2. h = mid - 1，mid = (0 + 1)/2 = 0，当前位置，27 > 13，27插入位置在13的高半区
3. low = mid + 1，mid = (1 + 1)/2 = 1，27 < 38，27的插入位置在38低半区
4. high = m - 1 = 0，high < low，折半查找结束，27的插入位置在high之后，插入位置后面的元素后移

<table>
    <thead>
    <th>0</th>
    <th>1</th>
    <th>2</th>
    <th>3</th>
    <th>4</th>
    <th>5</th>
	<th>6</th>
    <th>7</th>
    </thead>
    <tr>
        <td>13</td>
        <td>38</td>
        <td>49</td>
        <td>65</td>
        <td>76</td>
        <td>97</td>
 		<td>27</td>
 		<td>49</td>
    </tr>
    <tr>
        <td>low</td>
        <td></td>
        <td>mid</td>
        <td></td>
        <td></td>
        <td>high</td>
		<td>27</td>
 		<td>49</td>
    </tr>		
	<tr>
        <td></td>
        <td></td>
        <td>27 < 49</td>
        <td></td>
        <td></td>
        <td></td>
		<td>27</td>
 		<td>49</td>
    </tr>
	<tr>
        <td>low/mid</td>
        <td>high</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
		<td>27</td>
 		<td>49</td>
    </tr>
	<tr>
        <td>27 > 13</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
		<td>27</td>
 		<td>49</td>
    </tr>
	<tr>
        <td></td>
        <td>low/mid/high</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
		<td>27</td>
 		<td>49</td>
    </tr>
	<tr>
        <td></td>
        <td>27 < 38</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
		<td>27</td>
 		<td>49</td>
    </tr>
	<tr>
        <td>high</td>
        <td>low</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
		<td>27</td>
 		<td>49</td>
    </tr>
	<tr>
        <td>13</td>
        <td>27</td>
        <td>38</td>
        <td>49</td>
        <td>65</td>
        <td>76</td>
		<td>97</td>
 		<td>49</td>
    </tr>
</table>

```cpp

int main()
{
	// a[0]为存储临时变量的位置
	int a[9] = { 0, 13, 38, 49, 65, 76, 97, 27, 49 };
	int low, high, mid;
	for (int i = 2; i <= 8; ++i){
		a[0] = a[i];
		low = 1;
		high = i - 1;
		while (low <= high){
			mid = (low + high) / 2;
			if (a[mid] > a[0]){
				high = mid - 1;
			}
			else{
				low = mid + 1;
			}				
		}
		for (int j = i - 1; j >= high + 1; --j){
			a[j + 1] = a[j];
		}
		a[high + 1] = a[0];
	}
	int j = 0;
	while (j < 8){
		printf("%d ", a[j]);
		++j;
	}
	return 0;
}

```

### 时间复杂度分析

折半插入排序适合关键字数较多的场景，与直接插入排序相比，折半插入排序在查找插入位置上面所花的时间大大减少。

折半插入排序在关键字移动次数上面和直接插入排序是一样的，所以时间复杂度和直接插入排序还是一样的。

可知折半插入排序的时间复杂度最好情况为O(nlog2n)，最差情况为O(n^2)，平均情况为O(n^2)。

### 空间复杂度分析

同直接插入排序，O(1)