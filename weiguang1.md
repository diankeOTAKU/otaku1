# <center><font color=blue>微光招新题之计算机系统1</font></center>
## 第一个程序
### 1.高级计算机语言与低级计算机语言，各有什么优劣，你更喜欢哪一类计算机语言？
**答：**
|   | 高级计算机语言 | 低级计算机语言  |  
|:--------:|:--------:|:--------:|  
| 优点   | 1.代码易于理解和编写<br>2.可以在不同的操作系统和硬件上运行  |  1.执行效率高<br>2.可以优化内存的使用 <br>3.不依赖特定的操作系统和平台|  
| 缺点   |  1.执行效率通常低于低级语言<br>2.消耗更多资源（如内存等） |  1.代码难以阅读和编写<br>2.开发效率低 <br>3.难以在不同的硬件和操作系统上移植 |    

鼠鼠我更喜欢高级计算机语言，因为应用范围更广，学起来有挑战性。


### 2.尝试解读hello.c中每一行的内容
**答：**
  第一行：这是一个预处理的指令，只有引入了这个之后才能用“printf”来打印文本
  第二行：类似于一种固定搭配（？），像是一个入口，所有程序必须经由它才能运行
  第三行：它调用了来自stdio.h的printf()函数，使括号中的文本（即字符串）可以显示出来
  第四行：它表示上述代码运行结束，貌似可以用来判断是否成功执行
  第五行：说明main函数的结束

  ### 3.删去该程序的哪一行不会影响运行结果？
  **答：**
  显然是 “return 0;”这一行，我猜可能是因为这一行代码并没有实际含义，也有可能是程序运行自动添加等等。以下为图证：
  [![pA30YMq.png](https://s21.ax1x.com/2024/10/01/pA30YMq.png)](https://imgse.com/i/pA30YMq)

### 4.int类型是计算机存储什么元素的方式？为什么main函数要使用int进行声明/定义？
**答：**
int 类型用于存储整数值.
main函数结束时会有一个return环节，会return数值给main（0表示成功，其他表示失败），故需要用能存储整数值的int来接收（以上纯为个人见解，不对勿喷qwq）

### 5.请调整上述程序的内容，使其输出内容改为Hello glimmer!并附上运行截图
**答：**
如图所示：
[![pA3B9ln.png](https://s21.ax1x.com/2024/10/01/pA3B9ln.png)](https://imgse.com/i/pA3B9ln)

## 基础语法应用の天才黑客小明
```
#include <stdio.h>  

int main() 
{
    int code;
    int danyihao = 0; 

    printf("Show me your code, please.\n");
    while (danyihao == 0) 
    {
        scanf("%d", &code);

        if (code >= 100000 && code <= 999999)
        {
            printf("I am super hacker!\n");
            danyihao = 1;
        }
        else 
        {
            printf("Fake code!\nPlease re-enter a correct one!\n");
        }
    }

    return 0;
}
```

## 课后题

```

#include <stdio.h>  

int dan(int a, int b);

int main()
{
    int m, n;
    int p = 1;

    printf("哦哈哟，仙贝~\n请输入两个整数 m 和 n 喵~ (0 < m, n < 2^31，千万千万不要输入小数，否则鼠鼠我会生气捏):\n ");

    while (p)
    {
        scanf_s("%d %d", &m, &n);
        if (m > 0 && m < 2147483648 && n  > 0 && n < 2147483648)
        {
            int result = dan(m, n);
            printf("整数 %d 和 %d 的最大公约数是 %d です ★！\nCiallo～(∠·ω< ) ⌒ ★ ！​", m, n, result);
            p = 0;
        }
        else
        {
            printf("m 和 n 必须是在 0 < m, n < 2^31 范围内的整数喵~ ★!（嫌弃颜.jpg)\n请重新输入喵~：\n");
            p = 1;
        }
    }

    return 0;
}

int dan(int a, int b)
{
    while (b != 0)
    {
        int temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}
```