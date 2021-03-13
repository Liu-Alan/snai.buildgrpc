# snai.buildgrpc
Go生成Grpc

参考：https://www.imooc.com/article/274716

3 生成
把protocbuf 生成器和proto文件放在一个目录下，执行

protoc --go_out=plugins=grpc:. *.proto   //"."和"*"之间有个空格，不然会出错
protoc -I=proto --go_out=plugins=grpc:. base.proto
“*”换成你的proto文件名

如果指定proto文件路径可以加“-I”来指定，“-I”是“–proto_path”的简写

protoc -I=proto --go_out=plugins=grpc:. *.proto
如果想生成文件后都放到另外一个目录下，比如放到grpc目录下

protoc -I=proto --go_out=plugins=grpc:./grpc *.proto
嫌每次都要输入命令行可以写成批处理，如图
