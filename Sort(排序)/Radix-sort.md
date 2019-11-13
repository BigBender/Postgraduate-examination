## 基数排序

- **最高位优先(Most Significant Digit first)**

- **MSD**：先按最高位排成若干子序列，然后再对每个子序列按次高位排序。

- **最低位优先(Least Significant Digit first)**

- **LSD**：先按最低位排成若干子序列，然后再对每个子序列按次低位排序。

### 示例

- 对序列：**321，156，57，46，28，7，331，33，34，63** 进行基数排序，按照最低位优先，描述排序过程

- 注意：关键字从桶的**上方**放入，桶的**下方**取出。

- 第一趟：按个位

- 首先根据个位数的数值，在走访数值时将它们分配至编号0到9的桶子中

<table style="border-collapse:collapse">
    <thead>
    <th>0</th>
    <th>1</th>
    <th>2</th>
    <th>3</th>
    <th>4</th>
    <th>5</th>
	<th>6</th>
	<th>7</th>
	<th>8</th>
	<th>9</th>
    </thead>
    <tr>
        <td></td>		
        <td>331<br/>321</td>
		<td></td>
        <td>063<br/>033</td>
        <td>034</td>        
        <td></td>
		<td>046<br/>156</td>
		<td>007<br/>057</td>	
		<td>028</td>
		<td></td>
    </tr>
</table>

- 第二趟：按十位

- 将数从桶子下面取出，重新拼接

- 321 331 033 063 034 156 046 057 007 028

- 接着再进行一次分配，这次是根据十位数来分配

<table style="border-collapse:collapse">
    <thead>
    <th>0</th>
    <th>1</th>
    <th>2</th>
    <th>3</th>
    <th>4</th>
    <th>5</th>
	<th>6</th>
	<th>7</th>
	<th>8</th>
	<th>9</th>
    </thead>
    <tr>
        <td>007</td>				
        <td></td>
		<td>028<br/>321</td>
		<td>034<br/>033<br/>331</td>
        <td>046</td>
        <td>057<br/>156</td>        
        <td>063</td>
		<td></td>
		<td></td>	
		<td></td>
    </tr>
</table>

- 第二趟：按百位

- 将数从桶子下面取出，重新拼接

- 007 321 028 331 033 034 046 156 057 063

- 接着再进行一次分配，这次是根据百位数来分配

<table style="border-collapse:collapse">
    <thead>
    <th>0</th>
    <th>1</th>
    <th>2</th>
    <th>3</th>
    <th>4</th>
    <th>5</th>
	<th>6</th>
	<th>7</th>
	<th>8</th>
	<th>9</th>
    </thead>
    <tr>
        <td>063<br/>057<br/>046<br/>034<br/>033<br/>028<br/>007</td>				
        <td>156</td>
		<td></td>
		<td>331<br/>321</td>
        <td></td>
        <td></td>        
        <td></td>
		<td></td>
		<td></td>	
		<td></td>
    </tr>
</table>

- 从桶中取出

- 最终结果：007 028 033 034 046 057 063 156 321 331


### 时间复杂度分析

- 平均和最坏情况下都是O(d(n+rd))

- n为序列的关键字数

- d为关键字的关键字位数，如930，由3位组成，d=3

- rd是关键字基的个数，这里的基指构成关键字的符号，如关键字为数值时，构成关键字的符号就是0~9这些数字，一共10个

### 空间复杂度分析

- 每个桶实际上是一个队列，需要头尾指针，共有rd个桶，需要2rd个存放指针的空间

- 因此O(rd)。