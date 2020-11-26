### windows 使用
 * 主要是结合gvp使用，如果不使用gvp也可以
   + 安装包的时候把包安装到GOPATH指定的第一个目录中，所以只要设置对GOPATH就行，不管是手动设置还是通过gvp
   
 * 使用命令：gpm-local name package
   1. source gvp
     + 指定GOPATH
   2. cd package目录
   
   3. gpm-local name package
     + 将当前目录软链到GOPATH下名为package
   
 * 使用命令：gpm-local to path/package
   1. source gvp 
   2. gpm-local to path/package
     + 将path路径下的package自动链接到GOPATH目录，名称为package
     
   + windows   
     `gpm-local to E:\\xxx\xxx\hello`
   + linux   
     `gpm-local to /e/xxx/xxx/hello`  
   
   
   
   