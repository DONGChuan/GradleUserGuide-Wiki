### 22.7.1.Source Set 属性
下表列出了 Source Set 的一些重要属性, 更多细节请查看 [SourceSet](https://docs.gradle.org/current/dsl/org.gradle.api.tasks.SourceSet.html) 的 API 文档.

**表22.9.java 插件- Source Set 属性**

配置名称 | 类型 | 默认值                                     | 描述
------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------- | --------------------------------------------------------------------------------------------
name | String (read-only) | Not null | 用来识别source set的名称
output              | [SourceSetOutput](https://docs.gradle.org/current/dsl/org.gradle.api.tasks.SourceSetOutput.html)(read-only)                                                               | Not null                                | source set的输出文件,包含其编译的classes和resources
output.classesDir   | File                                                                                                                                                                      | buildDir/classes/name                   | 在该目录下生成存放这个source set的classes文件
output.resourcesDir | File                                                                                                                                                                      | buildDir/resources/name                 | 在该目录下生成存放这个source set的resources文件
compileClasspath    | [FileCollection](https://docs.gradle.org/current/javadoc/org/gradle/api/file/FileCollection.html)                                                                         | compileSourceSet configuration          | 这个source set编译时使用的classpath
runtimeClasspath    | [FileCollection](https://docs.gradle.org/current/javadoc/org/gradle/api/file/FileCollection.html)                                                                         | output + runtimeSourceSet configuration | 执行当前source set的classes文件时的classpath
java                | [SourceDirectorySet](https://docs.gradle.org/current/javadoc/org/gradle/api/file/SourceDirectorySet.html)(read-only)                                                      | Not null                                | 当前source set的java源文件,仅包含存在于java目录下的所有.java文件,排除其他任何文件.
java.srcDirs        | Set<File>.可以设置为在[Section 15.5, “Specifying a set of input files”](https://docs.gradle.org/current/userguide/working_with_files.html#sec:specifying_multiple_files)中描述的任何值 | [projectDir/src/name/java]              | 该source set的包含java源文件的目录
resources           | [SourceDirectorySet](https://docs.gradle.org/current/javadoc/org/gradle/api/file/SourceDirectorySet.html)(read-only)                                                      | Not null                                | 该source set的资源,只包含存在于resource目录吓得资源文件,会排除在resource下的所有.java文件,其他插件,如Groovy插件会在该集合中排除一些其他的文件.
resources.srcDirs   | Set<File>.可以设置为在[Section 15.5, “Specifying a set of input files”](https://docs.gradle.org/current/userguide/working_with_files.html#sec:specifying_multiple_files)中描述的任何值 | [projectDir/src/name/resources]         | 该source set的包含资源文件的目录
allJava             | [SourceDirectorySet](https://docs.gradle.org/current/javadoc/org/gradle/api/file/SourceDirectorySet.html)(read-only)                                                      | java                                    | 该source set的所有.java文件。一些插件，如Groovy插件，添加额外的Java源文件到这个集合。
allSource           | [SourceDirectorySet](https://docs.gradle.org/current/javadoc/org/gradle/api/file/SourceDirectorySet.html)(read-only)                                                      | resources + java                        | 该source set的所有源文件。这包括所有的资源文件和所有Java源文件。一些插件，如Groovy插件，添加额外的源文件到这个集合。
