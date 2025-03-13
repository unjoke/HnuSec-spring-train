# 攻防世界基础题单
## view_source
获取在线场景，进入场景后，在firefox中摁下F12，通过查看器可以找到flag。
![7803ad9a4a6a9c6897f2c21c5f2c1b39](https://github.com/user-attachments/assets/c36eca5a-59b7-4f2f-8832-f4d405186ab3)
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
访问 flag_is_h3re.php，成功找到 FLAG。
![112071e5c546019f2b3ec1e924513a2f](https://github.com/user-attachments/assets/6305d370-bdd5-434d-8c6f-34e5161fac45)
