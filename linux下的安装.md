安装包下载地址为：https://golang.org/dl/。
如果打不开可以使用这个地址：https://golang.google.cn/dl/。

1、将文件下载到服务器文件夹下，我的software
wget https://dl.google.com/go/go1.13.1.linux-amd64.tar.gz
2、解压到/usr/local目录下
tar -zxf go1.13.1.linux-amd64.tar.gz -C /usr/local
3、将 /usr/local/go/bin 目录添加至PATH环境变量
export PATH=$PATH:/usr/local/go/bin
4、验证安装是否成功
go version  查看版本号go version go1.13.1 linux/amd64
 也可以新建go文件测试
 vim test.go
 packeage main  //定义了包名
 import "frm" //告诉Go编译器，这个程序使用frm包函数，注意这里是双引号
 func main(){  //程序开始执行函数
    frm.Println("Hello World");//注意大小写
 }
 
 



