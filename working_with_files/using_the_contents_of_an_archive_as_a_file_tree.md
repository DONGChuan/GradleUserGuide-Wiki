# 使用一个归档文件的内容作为文件树

你可以使用 ZIP 或者 TAR 等压缩文件的内容作为文件树,  `Project.zipTree()` 和 `Project.tarTree()` 方法返回一个 `FileTree` 实例, 你可以像使用其他文件树或者文件集合一样使用它.例如,你可以使用它去扩展一个压缩文档或者合并一些压缩文档.

**例 15.7 使用压缩文档作为文件树**
**build.gradle**
```
// 使用路径创建一个 ZIP 文件
FileTree zip = zipTree('someFile.zip')

// 使用路径创建一个 TAR 文件
FileTree tar = tarTree('someFile.tar')

//tar tree 能够根据文件扩展名得到压缩方式,如果你想明确的指定压缩方式,你可以使用下面方法
FileTree someTar = tarTree(resources.gzip('someTar.ext'))
```








