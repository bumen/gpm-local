### windows 使用
 * 主要是结合gvp使用，如果不使用gvp也可以
   + 安装包的时候把包安装到GOPATH指定的第一个目录中，所以只要设置对GOPATH就行，不管是手动设置还是通过gvp
   
 * 使用命令：gpm-local me package 
   + 这个是原来gpm-local name的原始作用（我修改了name命令）
   1. source gvp
   2. gpm-local me package 
     + 将当前package 连接到自己的依赖中（自己包中依赖自己的时候使用）
     
   > 这个在windows使用ln -s 会有循环引用的问题，所以windows不要这么使用。（其实是文件拷贝，不是软链接）
   > 有时间写一个bat的，使用mklink就可解决，或者将当前package 加入到上层目录的.godeps, 然后将上层目录也加入到GOPATH中。（gpm-local name的原始这是这么用的）
 
   * 目录结构
     + 将/xx/xx/go/.godeps, /xx/xx/go/hello/.godeps都加入到gopath中
     + hello.go中 import "hello/world", 然后就可以调用world.go中的接口了
   ``` 
     go
       .godeps
       hello
         .godeps
         world
            world.go
         hello.go
   ```
   
 * 关于git bash中创建windows软链接
   + 似了使用secpol.msc 修改权限，结果不启作用
   + 似了MSYS=winsymlinks:nativestrict ln -s link target 也不启作用，或是CYGWIN=winsymlinks:nativestrict ln -s link target 
   + 似了启动开发者模式，这个是可以用的即，mklink /D 不需要管理员权限了
   + 最终使用 cmd <<< "mklink /J link target" > /dev/null, 不需要管理员权限，也不需要开发者模式。
   
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
   
   
   
   
   