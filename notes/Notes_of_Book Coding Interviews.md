### Introduction
The purpose of writing this post is recording some critical point of the book : **"Coding Interviews: Questions, Analysis and Solutions"**.

For efficiency, I'll first write the notes in Chinese and translate them into Engish version in the future.

#### 2.3.1

- 数组占据一块连续的内存，并按照顺序存储数据。

- 创建数组时，需要根据数据预先分配内存。因此数组的空间效率不是很好，常会有空闲的区域没有被利用。

- 由于数组中的内存是连续的，因此可以根据下标在*O(1)*时间复杂度下读/写元素，因此它有较高的时间效率。

- 可以用数组实现简单的哈希表。

- 使用动态数组可解决数组的空间效率不高的问题，例如C++的STL中的vector。

- 但是使用动态数组时，要尽量减少改变数组容量大小的操作次数，避免带来额外开销。这是由于动态数组一开始会分配较小的空间来避免浪费。随着数据添加到动态数组中，当数据量超过动态数组当前的容量时，会新开辟一块更大的空间，把旧的数据复制到新的空间中，再把之前的内存进行释放。

- STL的vector每次扩充容量时，新的容量都是旧的容量的2倍。

- 一个说明数组和指针区别的例子：

```C
int GetSize(int data[])
{
	return sizeof(data);
}

int main()
{
	int data1[] = {1, 2, 3, 4, 5};
	int* data2 = data1;
	
	int size1 = sizeof(data1);
	int size2 = sizeof(data2);
	int size3 = GetSize(data1);
	
	cout << size1 << "," << size2 << "," << size3 << endl;
	return 0;
}
```

```
output:
20, 4, 4
```

- 数组名是一个指针，它指向数组的第一个元素。32位系统，对任意类型的指针求sizeof，得到的结果都将是4。

- 当数组作为函数的参数进行传递时，数组就会自动退化为同类型的指针。因此GetSize函数实则是在求一个int类型指针的size，而非整个数组的size。