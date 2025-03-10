## 攻防世界基础题单：view_source
进入场景==>F12==>菜单中的“元素”==>查看网页前端代码即可获得flag
## 攻防世界基础题单：get_post
### 1. get传参

   直接在地址栏后加?a=1,回车
### 2. post传参

   在hackbar中
    ![](vx_images/68273369175441.png)

## 本次作业flag 

查看源码  
flag{we1c0me_t0_CTF!}
![](vx_images/34196413227125.png)
## python脚本
```
import hashlib
def find_md5_with_prefix(prefix):
    target_prefix = prefix
    i = 0
    while True:
        # 将整数转换为字符串并进行MD5加密
        original_value = str(i)
        md5_hash = hashlib.md5(original_value.encode()).hexdigest()

        # 检查MD5哈希的前6位是否匹配目标前缀
        if md5_hash[:6] == target_prefix:
            print(f"找到匹配的值: {original_value}")
            print(f"MD5哈希: {md5_hash}")
            break

        i += 1
if __name__ == "__main__":
    find_md5_with_prefix("19ca14")
```

## php一些基础语法学习（寒假学了一点点没做笔记，敲了个登录就当作业吧QwQ）
```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>登录</title>
		<link rel="stylesheet" type="text/css" href="./login.css">
		<?php
			$connect=mysqli_connect("localhost","root","root");//打开一个数据库连接
			$select=mysqli_select_db($connect,"data");//设置或更改连接的默认数据库，后面接数据库名
			//var_dump($select);//查看连接是否成功
			mysqli_query($connect,"SET NAMES 'utf8'");//设置字符集为utf8*/
		?>
	</head>
	<body class="container1">
		<form action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>" method="post" autocomplete="on">
			<table class="container2">
				<tr>
					<td><h1>登录</h1></td>
				</tr>
				<tr>
					<td><input type="text" placeholder="用户名" class="username" name="username"></td>	
				</tr>
				<tr>
					<td><input type="password" placeholder="密码" class="passwd" name="password"></td>	
				</tr>
				<tr>
					<td><input type="submit" class="container3" value="Login" name="login"></input></td>
				</tr>
				<tr>
					<td>没有账号去<a href="register.php">注册</a></td>
				</tr>
				<tr>
				 <td>
					<div class="check">
						<?php
							if(isset($_POST["login"]))
							{
								$username=$_POST["username"];
								$password=$_POST["password"];
								$check="select password from users where username='$username'";//因为设置了密码不能为空，所以如果查出来有值说明注册过，没有值说明没注册过
								$result=mysqli_query($connect,$check);
								$arr=mysqli_fetch_row($result);
								if($arr!=NULL&&$arr[0]==$password)
								{
									echo "<script>alert(\"登陆成功\");</script>";
								}else
								{
									echo "<script>alert(\"密码错误\");</script>";
								}
							}
						?>
					</div>
				 </td>	
				</tr>
			</table>
		</form>
	</body>
</html>
```

## RCE_writeup
### easyrce
![IMG_20250310_201013](vx_images/203444756791729.jpg)
可以看到源码中要以get方式传一个url参数，然后将其放入了eval（）函数中，此函数能将括号中的字符串视为命令运行
常见的系统命令执行函数还有
passthru()

exec()

shell_exec()

popen()

proc_open()

pcntl_exec()
考虑上传系统命令查看根目录
![Screenshot_2025-03-10-20-18-09-028_com](vx_images/556926102365644.jpg)
查看flag文件
![屏幕截图 2025-03-10 115708](vx_images/158316197493369.png)
### jicao
![屏幕截图 2025-03-10 114831](vx_images/213308334322052.png)
由源码可知要求以post传参上传一个id=wllmNB，以get传参上传一个一个json数组，且键为'x'的值为'wllm'![屏幕截图 2025-03-10 114706](vx_images/570255906128593.png)
### caidao
![屏幕截图 2025-03-10 224950](vx_images/266505649215211.png)
要以post传参一个wllm,用hackbar传一个wllm=systen("ls /");![屏幕截图 2025-03-10 225246](vx_images/385748471947830.png)
然后查看flag文件
![屏幕截图 2025-03-10 225455](vx_images/109075908279927.png)
### babyrce
![屏幕截图 2025-03-10 230909](vx_images/175781854130549.png)
根据源码提示，用burp抓包后（hackbar也行）cookie中admin=1
![屏幕截图 2025-03-10 230327](vx_images/207644774099732.png)
得到进一步的代码
php基础薄弱，不知道preg_match的作用

![屏幕截图 2025-03-10 230531](vx_images/301343709447759.png)
搜索后得知preg_match在php中用于执行正则表达式，参数有 pattern--正则表达式模式,subject--要搜索的字符串, matches--如果提供，匹配结果将储存在此数组中,flags--用于控制匹配行为的标志，offset--从字符串指定位置开始搜索
那么代码中的preg_match就应该是检查ip中是否存在空格
由于查看根目录中的命令含有空格，所以看了下别人的wp得知${IFS}可以代替空格
![屏幕截图 2025-03-10 232941](vx_images/504115924039699.png)
![屏幕截图 2025-03-10 233200](vx_images/115713502516367.png)



