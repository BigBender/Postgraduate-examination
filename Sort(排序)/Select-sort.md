## 简单选择排序 
 
首先选出最小的元素，把它移到a[0]。然后在剩余的n-1个元素中，找出最小的元素，把它移到a[1]。

如此反复，直到剩下一个元素。

### 示例

对序列：**6，5，8，4，3，1** 进行简单选择排序

![image](https://github.com/YC-L/hello-world/blob/master/imgs/Sort2.png)

* 图中灰色部分代表待排序列
* 图中透明部分代表已排序列
* 图中黑色上标代表交换位置的元素

```cpp

int main()
{
	int a[10] = { 6,5,8,4,3,7 };

	int min, j, temp;
	for (int i = 0; i < 6; ++i){
		min = i;
		for (j = i + 1; j < 6; ++j){
			if (a[j] < a[min]){
				min = j;
			}				
		}
		if (min != i){
			temp = a[min];
			a[min] = a[i];
			a[i] = temp;
		}
	}
	j = 0;
	while (j < 6){
		printf("%d", a[j]);
		++j;
	}
	return 0;
}

```

### 时间复杂度分析

将最内层的循环视为关键操作，执行次数是n(n-1)/2，时间复杂度为O(n^2)。

### 空间复杂度分析

算法所需的辅助存储空间不随待排序列规模变化而变化，是个常量，O(1)。