主要的代码构成有：linux.s，record-def.s,read_record.s,write_record.s。这四个是从ppt上面抄下来的。主要的功能代码在read_write.s里面。运行./read_write就可以运行。

其中的input.dat是由ppt中的生成record的方法生成的一个数据。应用代码为read_test.s,运行./read_test就可以生成这个文件。

最终的结果就是将input.dat文件之中的第320个字符的ascii码+1，由“-”，变成“.”。

文件的编译方式为：
as read_record.s -o read_record.o --32
as write_record.s -o write_record.o --32
as read_write.s -o read_write.0 --32
ld read_write.o read_record.o write_record.o -m elf_i386 -o read_write
最终生成可执行文件。

