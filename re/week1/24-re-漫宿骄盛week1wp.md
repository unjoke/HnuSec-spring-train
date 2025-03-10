![](https://cdn.nlark.com/yuque/0/2025/png/49936689/1741076920611-0eaf314d-9160-45c7-8d68-9591c7c66770.png)

输入一个数据，然后从后向前对其中的数据进行异或，然后和global的数据进行比较.

global  
![](https://cdn.nlark.com/yuque/0/2025/png/49936689/1741076985069-fecf6986-76b6-40b5-b238-a58e4a3ce26c.png)

exp

```cpp
#include <stdio.h>
#include <string.h>

int main() {
    unsigned char a[] =
    {
      102,  10, 107,  12, 119,  38,  79,  46,  64,  17, 
      120,  13,  90,  59,  85,  17, 112,  25,  70,  31, 
      118,  34,  77,  35,  68,  14, 103,   6, 104,  15, 
       71,  50,  79,   0
    };
    char flag[33];
    for (int i = 0; i < 32; i++){
        flag[i] = a[i]^a[i+1];
        printf("%c", flag[i]);
    }

}
```

<h2 id="VRs62">flag{QianQiuWanDai_YiTongJiangHu}</h2>
