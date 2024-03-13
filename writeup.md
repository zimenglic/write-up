writeups：

reverse：

reverse_level_0:

程序直接点击运行会闪退，所以放到cmd中运行：在cmd中转到文件所在的位置，执行exe文件得到flag

reverse_level_1:

将food_sellor_said用base_64转化成flag



web：

get_problem:

用postman发送参数

 

misc：

misc2：

照片只有一半 写一个py脚本判断照片原来的大小

```
import os
import binascii
import struct
crcbp=open("1.png",'rb').read()
for i in range(2000):
    for j in range(2000):
        data=crcbp[12:16]+struct.pack('>i',i)+struct.pack('>i',j)+crcbp[24:29]
        crc32=binascii.crc32(data)&0xffffffff
        if (crc32==0xE8D3C143):
            print(i,j)
            print("hex:",hex(i),hex(j))
```

得到大小：

![image-20240124183751958](C:\Users\LZM\AppData\Roaming\Typora\typora-user-images\image-20240124183751958.png)

在010中修改图片的尺寸，然后放大图片得到flag



crypto:

easy_crypto:

根据提示 用凯撒密码转换器

fence:

用的还不错的栅栏密码转换器：

栅栏数：5

http://www.metools.info/code/fence154.html