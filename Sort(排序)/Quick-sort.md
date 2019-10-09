## 快速排序

通过划分操作实现排序，以升序为例。每一趟选择当前所有子序列中的一个关键字作为枢轴（通常是第一个），将子序列中比枢轴小的移到枢轴前面，比枢轴大的移到枢轴后面。

### 一趟快速排序

对序列：**6，5，8，4，3，1** 进行快速排序，写出第一趟划分的过程。

<table>
    <thead>
    <th>0</th>
    <th>1</th>
    <th>2</th>
    <th>3</th>
    <th>4</th>
    <th>5</th>
    </thead>
    <tr>
        <td>6</td>
        <td>5</td>
        <td>8</td>
        <td>4</td>
        <td>3</td>
        <td>1</td>
		<td>枢轴:6</td>
    </tr>
	<tr>
        <td>i</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td>j</td>
    </tr>
</table>

使用j，从序列最右端开始扫描，直到遇到比枢轴6小的数1，停下，将1交换到序列前端i的位置。

<table>
    <thead>
    <th>0</th>
    <th>1</th>
    <th>2</th>
    <th>3</th>
    <th>4</th>
    <th>5</th>
    </thead>
    <tr>
        <td>1</td>
        <td>5</td>
        <td>8</td>
        <td>4</td>
        <td>3</td>
        <td></td>
		<td>枢轴:6</td>
    </tr>
	<tr>
        <td>i</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td>j</td>
    </tr>
</table>

使用i，从序列最左端开始扫描，直到遇到比枢轴6大的数8，停下，将8交换到序列后端j的位置。

<table>
    <thead>
    <th>0</th>
    <th>1</th>
    <th>2</th>
    <th>3</th>
    <th>4</th>
    <th>5</th>
    </thead>
    <tr>
        <td>1</td>
        <td>5</td>
        <td></td>
        <td>4</td>
        <td>3</td>
        <td>8</td>
		<td>枢轴:6</td>
    </tr>
	<tr>
        <td></td>
        <td></td>
        <td>i</td>
        <td></td>
        <td></td>
        <td>j</td>
    </tr>
</table>

使用j，从右端往左扫描，直到遇到比枢轴6小的数3，停下，将3交换到序列前端i的位置。

<table>
    <thead>
    <th>0</th>
    <th>1</th>
    <th>2</th>
    <th>3</th>
    <th>4</th>
    <th>5</th>
    </thead>
    <tr>
        <td>1</td>
        <td>5</td>
        <td>3</td>
        <td>4</td>
        <td></td>
        <td>8</td>
		<td>枢轴:6</td>
    </tr>
	<tr>
        <td></td>
        <td></td>
        <td>i</td>
        <td></td>
        <td>j</td>
        <td></td>
    </tr>
</table>

使用i，从左端往右扫描，找不到比枢轴6大的数，直到i与j重合，停下，将枢轴6放到该位置。

<table>
    <thead>
    <th>0</th>
    <th>1</th>
    <th>2</th>
    <th>3</th>
    <th>4</th>
    <th>5</th>
    </thead>
    <tr>
        <td>1</td>
        <td>5</td>
        <td>3</td>
        <td>4</td>
        <td>6</td>
        <td>8</td>
		<td>枢轴:6</td>
    </tr>
	<tr>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td>ij</td>
        <td></td>
    </tr>
</table>

第一趟划分结束

按同样的方法，将序列{1,5,3,4}和序列{8}进行划分，经过几趟划分，最终得到确定的有序序列。

### 时间复杂度分析

快速排序最好情况下的时间复杂度为O(nlog2n)，待排序列越接近无序，该算法效率越高

最坏情况下的时间复杂度O(n^2)，待排序序列越有序，该算法效率越低

平均情况下时间复杂度为O(nlog2n)

快速排序的排序趟数，与初始序列有关。

### 空间复杂度分析

该算法空间复杂度为O(log2n)，快速排序是递归进行的，递归需要栈的辅助。