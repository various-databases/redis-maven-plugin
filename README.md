redis-maven-plugin [![Build Status]
==================

> 嵌入式redis服务器，纯Java的Maven3版本.，基于https://github.com/spullara/redis-protocol。


基本示例
-----------------

添加该插件到pom中:
```xml
<plugin>
    <groupId>zx.soft.maven.plugins</groupId>
    <artifactId>redis-maven-plugin</artifactId>
    <version>1.1.0</version>
</plugin>
```

运行命令：
```mvn redis:run```

显示下面信息表示运行成功: 
```[INFO] Starting Redis(forked=false) server...```


集成测试示例
-----------------

(可参考这里面的示例: https://github.com/Various-DBs/redis-maven-plugin/tree/master/example )

插件配置如下:
```xml
<plugin>
    <groupId>zx.soft.maven.plugins</groupId>
    <artifactId>redis-maven-plugin</artifactId>
    <version>1.1.0</version>
    <configuration>
        <forked>true</forked>
    </configuration>
    <executions>
        <execution>
            <id>start-redis</id>
            <phase>pre-integration-test</phase>
            <goals>
                <goal>run</goal>
            </goals>
        </execution>
        <execution>
            <id>stop-redis</id>
            <phase>post-integration-test</phase>
            <goals>
                <goal>shutdown</goal>
            </goals>
        </execution>
    </executions>
</plugin>
```

然后使用下面的命令运行集成Redis后台测试： 
```mvn clean verify```

