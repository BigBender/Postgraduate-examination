## 线索二叉树

引入线索二叉树是为了加快查找结点前驱和后继的速度

### 中序线索二叉树

结点结构

<table style="border-collapse:collapse;">
	<tr>
		<td>lchild</td>
		<td>ltag</td>
		<td>data</td>
		<td>rtag</td>
		<td>rchild</td>
	</tr>
</table>

若 ltag=0 表示lchild为指针，指向结点的左孩子；如果 ltag=1，表示lchild为线索，指向结点的直接前驱

若 rtag=0 表示rchild为指针，指向结点的右孩子；如果 rtag=1，表示rchild为线索，指向结点的直接后继


```cpp

typedef struct TBTNode{
	char data;
	int ltag, rtag;
	struct TBTNode *lchild;
	struct TBTNode *rchild;
}TBTNode

```

#### 通过中序遍历线索化二叉树

```cpp    

void InThread(TBTNode *p, TBTNode *&pre){
	if(p != NULL){
		InThread(p->lchild, pre);	// 递归，左子树线索化
		if(p->lchild == NULL){		// 如果左孩子为空，建立当前结点的前驱线索
			p->lchild = pre;
			p->ltag = 1;
		}
		if(pre != NULL && pre->rchild == NULL){
			//	建立驱动结点的后继线索
			pre->rchild = p;
			pre->rtag = 1;
		}
		pre = p;					// pre 指向下一个结点p
		p = p->rchild;				// p指向一个新结点，pre和p分别指向的结点形成前驱后继对，为下一次线索的连接做准备
		InThread(p, pre);			// 递归，右子树线索化
	}
}

void createInThread(TBTNode *root){
	TBTNode *pre = NULL;	// 前驱结点指针
	if(root != NULL){
		InThread(root, pre);// 非空二叉树，线索化
		pre->rchild = NULL;	
		pre->rtag = 1;		// 处理中序最后一个结点
	}
}

```

#### 中序线索二叉树的遍历

```cpp

// 求以p为根的中序线索二叉树中，中序序列下的第一个结点的算法
TBTNode *First(TBTNode *p){
	while(p->ltag == 0){
		p = p->lchild;
	}
	return p;
}
// 求在中序线索二叉树中，结点p在中序下的后继结点的算法
TBTNode *Next(TBTNode *p){
	if(p->rtag == 0){
		return First(p->lchild);
	}else{
		return p->rchild;	// rtag == 1，直接返回后继线索
	}
}
// 中序线索二叉树上执行中序遍历的算法
void Inorder(TBTNode *root){
	for(TBTNode *p = First(root);p != NULL; p = Next(p)){
		Visit(p);// 访问结点
	}
}

```


#### 通过前序遍历线索化二叉树

```cpp

void preThread(TBTNode *p, TBTNode *&pre){
	if(p != NULL){
		if(p->lchild == NULL){
			p->lchild = pre;
			p->ltag = 1;
		}
		if(pre != NULL && pre->rchild == NULL){
			pre->rchild = p;
			pre->rtag = 1;
		}
		pre = p;
		// 在递归入口处，有限制条件，左、右指针不是线索才继续递归
		if(p->ltag == 0){
			preThread(p->lchild, pre);
		}
		if(p->rtag == 0){
			preThread(p->rchild, pre);
		}
	}
}

```

#### 先序线索二叉树的遍历

```cpp

void preorder(TBTNode *root){
	if(root != NULL){
		TBTNode *p = root;
		while(p != NULL){
			while(p->ltag == 0){
				Visit(p);
				p = p->lchild;
			}
			Visit(p);			// 此时p的左指针必为线索，但还没有被访问，要访问
			p = p->rchild;		// p的左孩子不存在，右指针若非空，不论是否为线索都指向其后继
		}
	}
}

```

#### 通过后续遍历线索化二叉树

```cpp

void postThread(TBTNode *p, TBTNode *&pre){
	if(p != NULL){
		postThread(p->lchild, pre);	// 递归，左子树线索化
		postThread(p->rchild, pre);	// 递归，右子树线索化
		if(p->lchild == NULL){		// 建立当前结点的前驱线索
			p->lchild = pre;
			p->ltag = 1;
		}
		if(pre != NULL && pre->rchild == NULL){	// 建立前驱结点的后继线索
			pre->rchild = p;
			pre->rtag = 1;
		}
		pre = p;
	}
}

```

#### 后序线索二叉树的遍历

1. 若结点x是二叉树的根，则其后继为空
2. 若结点x是其双亲的右孩子，或是其双亲的左孩子且其双亲没有右子树，其后继即为双亲结点
3. 若结点x是其双亲的左孩子，且其双亲有右子树，则其后继为双亲右子树上按后序遍历列出的第一个结点

