###### 查找文件

> https://blog.csdn.net/dcrmg/article/details/78000961

```bash
➜  ~ locate libtf2_ros.so 
/opt/ros/kinetic/lib/libtf2_ros.so

```

```
whereis+文件名
```

```
find / -name +文件名
```

```
locate+文件名
```

```
which+可执行文件名
```

###### LD_PREDLOAD 设置动态库加载顺序

>https://www.cnblogs.com/net66/p/5609026.html#:~:text=LD_PRELOAD%E6%98%AFLinux%E7%B3%BB%E7%BB%9F%E7%9A%84%E4%B8%80%E4%B8%AA%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F%EF%BC%8C%E5%AE%83%E5%8F%AF%E4%BB%A5%E5%BD%B1%E5%93%8D%E7%A8%8B%E5%BA%8F%E7%9A%84%E8%BF%90%E8%A1%8C%E6%97%B6%E7%9A%84%E9%93%BE%E6%8E%A5%EF%BC%88Runtime,linker%EF%BC%89%EF%BC%8C%E5%AE%83%E5%85%81%E8%AE%B8%E4%BD%A0%E5%AE%9A%E4%B9%89%E5%9C%A8%E7%A8%8B%E5%BA%8F%E8%BF%90%E8%A1%8C%E5%89%8D%E4%BC%98%E5%85%88%E5%8A%A0%E8%BD%BD%E7%9A%84%E5%8A%A8%E6%80%81%E9%93%BE%E6%8E%A5%E5%BA%93%E3%80%82%20%E8%BF%99%E4%B8%AA%E5%8A%9F%E8%83%BD%E4%B8%BB%E8%A6%81%E5%B0%B1%E6%98%AF%E7%94%A8%E6%9D%A5%E6%9C%89%E9%80%89%E6%8B%A9%E6%80%A7%E7%9A%84%E8%BD%BD%E5%85%A5%E4%B8%8D%E5%90%8C%E5%8A%A8%E6%80%81%E9%93%BE%E6%8E%A5%E5%BA%93%E4%B8%AD%E7%9A%84%E7%9B%B8%E5%90%8C%E5%87%BD%E6%95%B0%E3%80%82
>
>七、LD_PRELOAD运用总结

> 1. 定义与目标函数完全一样的函数，包括名称、变量及类型、返回值及类型等
> 2. 将包含替换函数的源码编译为动态链接库
> 3. 通过命令 `export LD_PRELOAD="库文件路径"`，设置要优先替换动态链接库
> 4. 如果找不替换库，可以通过 `export LD_LIBRARY_PATH=库文件所在目录路径`，设置系统查找库的目录
> 5. 替换结束，要还原函数调用关系，用命令`unset LD_PRELOAD` 解除
> 6. 想查询依赖关系，可以用`ldd 程序名称`