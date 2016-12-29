# node安装
## 进入官网
## 在相应的平台下，下载相应的版本，一个是稳定版，一个是最新版
**学习者可以下载最新半年，上线者下载稳定版，偶数是稳定版，奇数是最新版**
## 安装
### windows安装
1.  下载相应的安装文件，用两种安装包，一个是node.exe,一个是node.msi.node.msi包含了node.exe、npm，node.exe要添加到全局路径下，要选择 add to path ，将node.exe自动添加到全局路径下。安装成功后，可以命令行操作node -v 检测安装的版本。


#npm
1. 包管理工具  node package manage ，安装成功后，命令行 npm -v 检测安装是否成功，以及版本号。
2. 为了程序人员开发方便，给我们提供了一个管理包，不用担心你的模块和数据是否被别人看到，


#执行第一个程序
## 交互式方式运行node.js
1. node 回车，进入编译环境，ctrl+c退出编译环境。
2. 输入符合node.js语法的语句，回车后会立即得到结果，对你你输入的命令来进行相应。

##编译型运行node.js
1. 创建一个js文件
2. 在命令行进入文件所在的目录，通过 node node.js 来对这个js文件进行解析和执行。


#node.js运行环境的配置
## phpstrom 来配置node.js的环境
1. 打开配置项目，
      **webstrom不用配置，已经配置好相应的环境**
2. 打开plugins搜索node.js，找到安装，完成后重启编译器，重启后打开配置项
3. 在framework下能找到node and npm 。插件已经安装成功。
4. 首先让他可用，选择提示语言。


#node.js语法
**遵从ecmascript 6 语法内容**
1. 定义常量 const a=10;


#node.js全局对象

##js全局对象是window
1. node.js里有一个全局对象，global

###global的子对象
1. console

    1.1 console.log() 可以接受很多参数  在控制台输出消息  
    1.2 console.error() 在控制台输出一条错误的消息   
    1.3 console.time() 在程序运行前调用，记录当前的信息  
    1.4 console.timeEnd() 在程序运行完成后调用，也来记录程序完成后的信息  
    1.5 console.trace() 追踪程序中的堆栈的运行情况，用的少
    
2. modules

    2.1 概念  
        模块是node.js 区别于js最重要的概念，把每个文件都当做独立的作用域，每一文件就是一个模块，在当前模块下定义的所有变量或函数，都是属于该模块的，如果想定义全局的，必须通过global，在模块下定义的变量的作用范围只能在模块范围内，在global下定义的变量或函数，，具有全局的作用范围。   

    2.2 module exports 联系
        module.exports===exports 能够将当前模块下的值反射出去，让引用的模块获取相应的值 

        **二者为引用关系，如直接赋值，会导致联系断开**   

    2.3 在node.js中会分为三种模块，  
        2.3.1 自定义模块   
        2.3.2 内置模块   
        2.3.3 外部模块（包）

3. process
	用来操作或者是获取或者查看当前进程的相关信息

    3.1 stdin 标准的输入流，可以监控控制台输入的东西，
        事件 “data” process.stdin.on("data",fn)  
            主动触发事件 process.stdin.emit()   
            暂停 process.stdin.pause()      
            重启 process.stdin.remuse()   
 
        stdout 标准的输出流   二者都属于进程的对象  
    3.2 argv 用来获取命令行相关的参数【“执行的二进制文件”，“当前运行的文件”】  
    3.3 chdir（）改变进程运行的目录   
    3.4 cwd（）当前进程所在目录

###global 里面的方法
1. setInterval
2. setTimeout
3. clearInterval
4. clearTimeout
5. require("输入路径") 引入其他模块  
    require.cache  记录了当前文件所引用的所有模块  
    require.resolve("path") 将引用模块的相对路径转化为绝对路径


### 魔术常量

1. __dirname 当前文件运行的目录
2. __filename 当前运行的文件名

##node.js方法的稳定等级
0  废弃     已经废弃，不能使用  
1  试验     正在试验阶段，不建议使用，并可能随时废弃  
2  不稳定   在某些平台可以用，不稳定，不建议使用，时刻关注更新或废弃  
3  稳定     进入稳定阶段。即使改动也是改动底层的接口和性能，不影响使用  
4  冻结     已经很稳定，可以投入项目使用  
5  锁定     很长时间内不会升级/迭代，不接受修改（除非有大bug）


#文件系统
1.  打开
   fs.open(path,flags,mode,callback)   
    /*   path:路径        
         flags：打开方式     r   r+    a     w   
         mode：打开模式   
         callback：打开完成后执行的内容
    */
    
2. 读取
    fs.read(id,buffer,offset,length,position,callback)  
	/*   id: 打开文件的编号   
      buffer:要保存读取内容的容器   
      offset：在容器中存取的起始位置   
      length：在容器中存储的文件长度   
      position：将要读取的文件的位置   
      callback：读取完成后执行的回调函数*/  

3. 读取文件的详细信息     
    fs.stat(path,callback)
 
    /*path：文件路径   
    callback：读取完信息后执行的回调函数*/

    
4. 写入文件
    fs.write(fd，buffer，offset，length，position，callback)
	/*fd: 打开文件的编码   
      buffer：要写入的数据      
      offset：在文件的什么位置开始写入   
      length：要写入的长度    
      position：要从写入文件的什么位置开始，
      callback：写完后要执行的回调函数  
      */


5. 创建一个文件
   writeFile（）   
     /*1.文件名   
       2.写入的内容   
       3.设置的选项   
       4.写入完成后的回调函数

       创建一个文件，并且可以写入内容*/
 
6. 追加内容
    fs.appendFile（file，data，options，callback）   
    /* file:要操作的文件   
    data：要追加的内容   
    options：指定选项     
    callback   
    如果该文件存在，可以往里面追加内容*/  

7. 修改内容  
   fs.rename（oldpath，newpath，callback）   
    /* oldpath:原来名   
    newpath：新名*/

8. 删除文件   
   fs.unlink(path，callback)   
     /* path：要删除的文件*/
    
9. 读取文件  
   fs.readFile(file，options，callback)   
    /* file:要读取的文件   
      options：设置选项*/

10. 拷贝文件




>操作目录

1. 创建目录
   fs.mkdir（path，mode，callback）   
    /* path：创建的目录   
      mode：目录的模式   
      callback*/

2. 删除目录   
   fs.rmdir(path,callback)   
    /* path：要删除的目录  
      callback：删除后执行的回调函数*/


3. 创建cmd程序   
   3.1. 创建package.json文件  
   3.2. 在json文件里指定bin  
   3.3. 在指定的运行文件里，加   #！文件目录     /* 指定文件解析要调用的程序*/  
   3.4. 进入该目录，运行npm install -g /* 将该模块，打包到全局环境下*/  
   3.5  npm link==“abs” 运行程序




# stream

#### 流的概念，数据流，分为三种数据流
1. readStream   
    1.1 fs.createReadStream(path,options);   
	/* path：创建读取流要指定的文件路径                                                                                                                                               
	   options：flags <String>  
                encoding <String>  
                fd <Integer>  
				mode <Integer>  
				autoClose <Boolean>  
				start <Integer>  
				end <Integer>  
				highWaterMark <Integer>*/   
        1.1.1 事件   
			data  当数据读取的时候    
			close  当数据读完的时候   
		1.1.2 方法   
            pause（） 读取数据暂停   
			resume（）读取数据开始   
			pipe（） 管道 由读取流安全的传输到下一个流，保证了数据的安全，读入流>写入流，会暂停   读入流<写入流,会触发事件

2. writeStream  压缩一个文件 

    2.1 fs.createWriteStream( path,options);   
        2.1.1 事件   
			drain  当前内存数据完全写入流的时候触发   
			close  当数据全部写完的时候触发   
		2.1.2 方法  
            write（）要往写入流里面写入的数据   
3. stream.Duplex 双向数据流
  
   


