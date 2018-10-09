# sfip-app-archetype

服务JAVA项目构建(这里以命令行为例，eclipse等环境更方便):
mvn  archetype:generate -DarchetypeGroupId=com.github.yihaijun -DarchetypeArtifactId=sfip-app-archetype -DarchetypeVersion=1.0.6 -DgroupId=priv.yhj.test -DartifactId=app-test -Dversion=1.0.1 -DinteractiveMode=false -DarchetypeCatalog=local -X -e
然后cd app-test(进到你的artifactId对应目录)mvn install
就可以看到target目录下有了app-test-1.0.1.zip
