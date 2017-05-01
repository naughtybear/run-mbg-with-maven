# 使用Maven运行Mybatis Generator

### 1. pom.xml指定了依赖的插件包，并且定义了mybatisGenerator.xml中使用到的一些属性的值
> 例如：
```xml
    <properties>
        <jdbcDriver.classpath>E:\Work\tool-lib\mysql-connector-java-5.1.41.jar</jdbcDriver.classpath>
        <mybatis.generator.jdbcDriver>com.mysql.jdbc.Driver</mybatis.generator.jdbcDriver>
        <mybatis.generator.jdbcURL>jdbc:mysql://192.168.99.100:3306/test?characterEncoding=utf8&amp;useSSL=false</mybatis.generator.jdbcURL>
        <mybatis.generator.jdbcUserId>root</mybatis.generator.jdbcUserId>
        <mybatis.generator.jdbcPassword>test123456</mybatis.generator.jdbcPassword>

        <!-- Mapper/SqlProvider -->
        <java.client.target.dir>E:\Work\projs\java\spring-boot-sample\src\main\java</java.client.target.dir>
        <java.client.target.package>com.zzh.springboot.demo.dao.mapper</java.client.target.package>

        <!-- Model -->
        <model.target.dir>E:\Work\projs\java\spring-boot-sample\src\main\java</model.target.dir>
        <model.target.package>com.zzh.springboot.demo.model</model.target.package>

        <!-- XML Mapping file -->
        <mapper.target.dir>E:\Work\projs\java\spring-boot-sample\src\main\resources\mybatis</mapper.target.dir>
        <mapper.target.packge>mapper</mapper.target.packge>

        <mybatis.generator.tableNames>student,course_score</mybatis.generator.tableNames>
    </properties>
```
**您可以通过修改一些属性定义来满足自己的项目需求**

### 2. MBG配置文件 - src/main/resources/generatorConfig.xml
其中的大部分配置依赖于pom.xml中定义的属性，推荐经常容易变动的属性以pom中的属性方式进行引用。
**通常你只需要对table进行配置即可**


### 3. 配置好以上两步之后，执行下面命令
   ```mvn mybatis-generator:generate```

<br>

### 附录
[MGB](http://www.mybatis.org/generator/index.html)使用说明