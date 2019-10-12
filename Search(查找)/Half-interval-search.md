## 折半查找(二分查找)

### 仅适用于有序的顺序表

首先将给定值key与表中中间位置元素的关键字比较，若相等，查找成功，返回该元素的存储位置

若不等，则所需查找的元素只能在中间元素以外的前半部分或后半部分中

然后在缩小的范围内继续进行同样的查找，如此重复直到找到为止，或者确定表中没有所需查找的元素

```cpp

int Binary_Search(SeqList L, ElemType key){
	int low = 0, high = L.TableLen-1, mid;
	while(low <= high){
		mid = (low + hight)/2;
		if(L.elem[mid] == key){
			return mid;
		}else if(L.elem[mid] > key){
			high = mid-1;			// 从前半部分继续查找
		}else{
			low = mid+1;			// 从后半部分继续查找
		}
	}
	return -1;
}

```

![image](https://github.com/YC-L/Postgraduate-examination/blob/DataStructure/imgs/Half-interval-search.png)

折半查找过程的判定树(左小右大)

圆形结点表示一个记录，结点中的值为该记录的关键字值

矩形结点表示查找不成功的情况

查找成功时，查找长度为从根结点到目的结点的路径上的结点数

查找不成功时的查找长度为从根结点对应失败结点的父结点路径上的结点数

有序序列有n个元素，对应的判定树有n个圆形的非叶结点和n+1个方形的叶结点

查找成功平均查找长度

ASL=1/n ∑ li = 1/n(1*1 + 2*2 + ... + h*2^(h-1))=n+1/nlog2(n+1) - 1≈log2(n+1)-1

#### 仅适合于线性表的顺相互存储结构，不适合链式存储结构，切要求元素按关键字有序排列

- 因为折半查找需要方便定位查找区域，适合折半查找的存储结构必须具有随机存取的特性

#### 时间复杂度 O(log2n)，平均情况下比顺序查找效率高








