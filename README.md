# ZipSplitter
将zip文件以文件粒度快速拆分成多个zip文件，可用于MultiDex提速

通常将Zip文件按文件拆分成多个zip文件时，需要经历以下步骤：

    1、读取Zip文件
    
    2、将指定文件从Zip文件中解压到内存或磁盘
    
    3、将解压后的文件重新压缩成zip
    
    4、将得到的zip写入磁盘
    
此项目的作用是省去上述第2步和第3步，直接从Zip文件中按字节读取指定的文件的数据块，再将数据块写入磁盘，
并在数据块的末尾追加Zip文件格式所需的数据结构，形成一个新的zip文件。这样省去了解压和压缩的过程，提高
效率。

可用于MultiDex提速：

    MuliDex在安装dex2、dexN时，会先将dex文件从apk中解压出来，再压缩成一个dexN.zip包，再将这个
    Zip文件追加到classloader，使用此项目后可以省去解压和压缩过程，达到提速目的。
    
Zip文件格式参考：http://blog.sina.com.cn/s/blog_4c3591bd0100zzm6.html


