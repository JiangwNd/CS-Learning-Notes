### 比较三个数大小

* ###### C语言三个数字比较大小

https://blog.csdn.net/u012260672/article/details/50414050

```
int median(int a1, int b1, int c1);
int median(int a1, int b1, int c1) {
    int max = (a1 > b1 ? a1 : b1) > c1 ? (a1 > b1 ? a1 : b1) : c1;
    int min = (a1 < b1 ? a1 : b1) < c1 ? (a1 < b1 ? a1 : b1) : c1;
    return a1 + b1 + c1 - max - min;
}
```

* ###### 如何更简洁的比较3个数的大小

https://bbs.csdn.net/topics/240069884

```
private static int findMax(int a, int b, int c)
{
    return ((a > b ? a : b) > c) ? (a > b ? a : b) : c;
}
    
    
int[] arr = new int[3];
         
for(int i = 0;i <3 ;i++)
{
    if(arr[i] < arr[i+1])
    {
        min = arr[i];
    }
    if(arr[i] > arr[i+1])
    {
        max = arr[i];
    }
}
```

* ###### 



