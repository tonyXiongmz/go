go声明变量
 1、指定变量类型
 var name string
 var num int
 var name1,name2 string
 var num1,num2 int=1,2
 
 变量的初始值如果没有声明，int 0,float 0,bool false,string ""
 
 2、自行判断变量类型
 var name=true //bool
 
 3、省略var,注意:=左侧没有声明新变量或是已声明的变量都会报错，只能使用在函数体内部
 name := 'hha' //正确
 
 var name
 name := '哈哈' //错误
 
 4、全局变量，这种方式一般用来声明全局变量
 var (
  name = '哈哈'
  num int
 )
 
 注意事项：
 1、同一个变量两次初始化是不被允许的，可以重新赋值
 2、声明一个局部变量，如果没有用到会报错
 3、函数体外声明是全局变量
 4、全局变量和局部变量名称可以重复
 5、全局变量不能用：=定义
 声明常量
 const关键字
 const name string='wang'
 
 iota用法,初始值为0，每使用一次+1，占位也+1但不覆盖原有值
 const(
  i=iota // 0
  j=iota // 1
  k=6  // 6
  l=iota // 3
 )
 
 移位的用法，二进制的位移
 const(
  i=1<<iota // 1 0001<<0
  j=3<<iota // 6  0011<<1 0110
  k // 12 0011<<2 1100
  l // 24 0011<<3 0001 1100
 )
 
 条件判断语句
 if a<20 {
  if b<15{
  
  }
 } else {
 
 }
 //if条件里可以赋值,但只在if结构内有用!
 switch name {
  case 'zhang':
  case '王':
 }
 
 switch {
  case name='zhang':
  case name='王':
 }
 switch中默认break,switch后面可以没有表达式
 fallthrough的用法，使用 fallthrough 会强制执行后面的 case 语句，fallthrough 不会判断下一条 case 的表达式结果是否为 true。
 switch age{
   case 10:
    fallthrough  //添加此关键字以后，该条件下的结果不输出，输出下一个条件的结果
    case 20:
     fallthrough
     case 30:
     case 40:
     fallthrough
 }
 
 select { //和switch类似
  case 1:
  case 2:
  default:
 }
 
 循环语句
 for a:=0;a<10;a++{
  if a==8{
   continue;
  }
  if a==9{
   break;
  }
 }
 
 var a int = 10
 for a<20{
 
 }
 
 LOOP:for a<15{
  if a==12{
   goto LOOP //跳回LOOP，类似continue
  }
 }
 
 数组的定义
 var arr [5] int  定义数组
 arr := [3] int {1,2,4} 数组赋值
 arr := [...] int {3,4,6,7,8}
 var arr  [3][5] int  二维数组
 
 数组的循环
 for i:=0;i<len(arr);i++{
  fmt.Println(arr[i])
 }
 
 for i:=range arr {
  fmt.Println(arr[i])
 }
 
 for i,v := range arr {
  fmt.Println(i,n)
 }
 数组的长度不同代表的类型也不同
 go语言一般不用数组传值
 go语言没有数组类型，故数组不能作为整体返回，如果要改变某一个数组的值通过切片实现。
 
 切片slice//类似于array_slice
 var s []int
 arr := [...]int{1,2,3,4,5,6,7,5}
 s[0] = 11//arr相应的值会被改变
 切片的下标是可以向后扩展,但不可以向前扩展
 len长度
 cap隐形空间长度
 make 设置切片信息 s := make([] int ,16)
 s1 := make([] int ,10,32)
 copy(s2,s1)//将s1的信息copy到s2中
 append(s1,"10")新增内容
 
 强制类型转换，go语言中变量的类型必须是一致的，如果和定义不符，需要强制转换为同类型
 
 定义结构体
 type关键字定义结构体名 struct定义新的数据类型
 type people struct{
  var name string 
  var age int
  var height int
  var weight float
 }
 func main(){
  var men people
  men.name = '王'
 }
 
 map是无序集合，键值对的形式，但顺序是是可变的
 var m map[string]string
 make(map[string]string)
 people:=map[string]string//创建map
 people['name'] = '张三'
 people['class'] = '高三'
 
 people := map[string]string{'李四','王五'}
 len(people)//长度
 delete(people,'李四')  //删除map值
 命令源码文件
 声明自己属于main包
 库源码文件
 测试源码文件
