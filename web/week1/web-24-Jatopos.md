# 工具安装
HackBar

![69f6aaf9fc924c9decab4f8dd38a6ae8](https://github.com/user-attachments/assets/299e710c-5aba-4e67-82f4-1faf55bd532c)

BurpSuite

![QQ_1741861291613](https://github.com/user-attachments/assets/75d54315-e541-4694-ab38-a4505b859d9a)

Dirsearch & SQLmap & Typora & git

![](https://github.com/user-attachments/assets/0383d67a-eb5e-4978-b133-28b90830fd3a)

![QQ_1741860782970](https://github.com/user-attachments/assets/0c0bfe2d-33ff-4bed-9780-6820e3e86fed)

# 攻防世界基础题单
## view_source
获取在线场景，进入场景后，在firefox中摁下F12，通过查看器可以找到flag。

![](https://github.com/user-attachments/assets/c36eca5a-59b7-4f2f-8832-f4d405186ab3)

## get_post

GET 是最常见的 HTTP 方法之一。用 GET 给后端传参的方法是：在?后跟变量名字，不同的变量之间用&隔开，在url后添加/?a=1 即可发送get请求。

![142033240e726ea4421473bb459034e6](https://github.com/user-attachments/assets/4dde11ed-b55c-4fcf-a334-63431c39d053)

POST 用于将数据发送到服务器来创建/更新资源。

在hackbar中进行 POST 传参：复制get的url，选择postdata，填入b=2，选择execute。即可发送POST 请求，便可获得flag。

![c93338977e8d9569ffe2bc2c74de8faf](https://github.com/user-attachments/assets/05043a46-700a-49d6-8bf9-0b00a17632ea)

## robots

Robots 协议（也称为爬虫协议、机器人协议等）是网站与爬虫之间的一种默契约定，用于指导爬虫哪些页面可以抓取，哪些不可以抓取，从而保护网站的数据隐私、性能以及避免过度抓取对服务器造成负担。其本质是一个放置在网站根目录下的文本文件（通常命名为 robots.txt），里面包含了一系列规则，告诉搜索引擎爬虫或其他网络爬虫在抓取网站页面时应遵循的指令。

![QQ_1741859693664](https://github.com/user-attachments/assets/b018faa7-c612-4cc6-af05-10dd05607fe4)

先调用查看器访问源代码，没有发现flag，访问 robots 文件，在网址后添加robots.txt，找到有关 flag 的 php 文件。

![6f468e704a452ddd3933db6e4e4af7ca](https://github.com/user-attachments/assets/0e989289-c7b6-40a0-98a1-58a0fd4af76d)

访问 flag_is_h3re.php，成功找到flag。

![112071e5c546019f2b3ec1e924513a2f](https://github.com/user-attachments/assets/6305d370-bdd5-434d-8c6f-34e5161fac45)

# 项目隐藏flag
直接看README.md文件源代码可以找到 flag{we1c0me_t0_CTF!}

![3e25593536b4b1868cb42680703d4158](https://github.com/user-attachments/assets/b7597c5b-6f4f-42d0-87c9-a5e4d83899b3)

# python脚本（DeepSeek）
import hashlib

def find_md5_prefix(target_prefix):
    num = 0
    while True:
        candidate = str(num).encode()
        hash_hex = hashlib.md5(candidate).hexdigest()
        if hash_hex.startswith(target_prefix):
            return candidate.decode()
        num += 1

if __name__ == "__main__":
    target = '19ca14'
    result = find_md5_prefix(target)
    print(f"找到的值: {result}")

# PHP
## 写的第一段PHP代码
<!DOCTYPE html>
<html>
<body>
<h1>Welcome to Jatopos</h1>

<?php
echo "Hello CTF!";
?>

</body>
</html>

## PHP语法笔记
PHP是超文本预处理器。是运行在服务端的开源语言，它可以让Web开发人员快速的书写生成动态的页面。--*PHP是最好的语言！*

echo：输出

print：输出内容，输出成功后打印1

print_r：输出数组，打印变量

var_dump：输出数据的详细信息，带有数据类型，数据长度

*< !DOCTYPE html >*：声明文档遵循HTML5标准，必须出现在文档第一行，不是HTML标签

*< html >*：定义整个HTML文档的根元素，包裹所有网页内容

*< body >*：包含网页可见内容的主体部分（文本、图片、视频等）

*< h1 > < /h1 >*：显示最大的一级标题

*< ?php ... ? >*：PHP代码标识符
执行流程：
服务器解析PHP代码
执行echo语句输出内容
将结果嵌入HTML发送给客户端
安全特性：客户端无法看到原始PHP代码

*echo*：输出指定字符串到HTML中

PHP数据类型：整数型、浮点型、布尔型、字符串型

PHP变量必须以 $ 开头，区分大小写
unset() 来删除变量，销毁变量名。
isset() 用来检查变量是否被设置并且是否为空。

define(常量名,值) 定义变量

与其它语言不同的运算符：

== 比较值

=== 全等于，左边与右边相同：（大小以及数据的类型都要相同）

!==	不全等于，只有大小或者类型不同

@ 错误抑制符

PHP暂时只学了这么多⁽˙³˙⁾
