#### 嵌入方式
在win10终端中使用命令 copy /b niuyeye.jpg+guoyao.jpg test.jpg  
此命令将两张图片以二进制形式拼接起来，结果图片看起来仍然是原图片。  


#### 分离方法
使用linux中的binwalk，运行binwalk test.jpg   

得到结果：

```
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.01  
int1          int2            JPEG image data, JFIF standard 1.01
```

在linux中在文件目录下使用命令 dd if=test.jpg of=guoyao.jpg skip=int1 bs=1
得到最终结果
