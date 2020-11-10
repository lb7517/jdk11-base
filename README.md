#### jkd8升级jdk11分析工具

* * *
**升级最担心的就是被删除的模块！**
推荐IBM公司Liberty团队提供了一个十分好用的检测Toolkit程序，可以扫描应用程序二进制文件（.war），发现的任何潜在的Java 11问题并生成Html报告。绝对的大利器，详细内容直接查看IBM官方介绍：Scanner Kit。直接运行java -jar binaryAppScannerInstaller.jar，
按步骤安装有个lisence声明和目录指定，默认目录名wamt。
![1d5e53512fa7da531b6ff9671f3c9982.png](en-resource://database/717:1)


**参考文档中会有使用详细介绍，也可以参考下面测试例子（扫描很慢，要些耐心等:**
java -jar binaryAppScanner.jar Root.war --analyzeJavaSE --sourceJava=oracle8 --targetJava=java11 --output=./java11/RootReport.html


**注意:**

* window使用cmd执行或Powershell执行上面的命令，用git执行会乱码
* binaryAppScannerInstaller.jar 工具在[git的地址](https://github.com/lb7517/jdk8ToJdk11.git)