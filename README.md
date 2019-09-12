**mmall**

**util：工具类包；
vo：value object；
pojo：数据库对象；
common：公共类、常量**

**Git上传：**

    touch README.md
    
    touch .gitognore
    
    git init    
    
    git status  
    
    git add .
    
    git commit -am "first commit init project"
    
    git remote add origin https://github.com/Hluobo-gulu/mmall.git
    
    git branch
    
    git push -u origin master
    
    git pull
     
    git push -u -f origin master
    
    git branch -r
    
    git checkout -b v1.0 origin/master
    
    git push origin HEAD -u

**Git更新：**

    git add .
    
    git commit -am "project init commit"
    
    git push


**MyBits三剑客：**

    Mybatis-generator代码自动生成
    mybatis-generator是很好用的mybatis自动代码生成工具。手动写一个个实体类和mapper还有xml配置文件会很麻烦，
    使用mybatis-generator只需要简单的配置就能完成
    
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE generatorConfiguration
            PUBLIC "-//mybatis.org//DTD MyBatis Generator Configuration 1.0//EN"
            "http://mybatis.org/dtd/mybatis-generator-config_1_0.dtd">
    
    <generatorConfiguration>
        <!--导入属性配置-->
        <properties resource="datasource.properties"></properties>
    
        <!--指定特定数据库的jdbc驱动jar包的位置-->
        <classPathEntry location="${db.driverLocation}"/>
    
        <context id="default" targetRuntime="MyBatis3">
    
            <!-- optional，旨在创建class时，对注释进行控制 -->
            <commentGenerator>
                <property name="suppressDate" value="true"/>
                <property name="suppressAllComments" value="true"/>
            </commentGenerator>
    
            <!--jdbc的数据库连接 -->
            <jdbcConnection
                    driverClass="${db.driverClassName}"
                    connectionURL="${db.url}"
                    userId="${db.username}"
                    password="${db.password}">
            </jdbcConnection>
    
    
            <!-- 非必需，类型处理器，在数据库类型和java类型之间的转换控制-->
            <javaTypeResolver>
                <property name="forceBigDecimals" value="false"/>
            </javaTypeResolver>
    
    
            <!-- Model模型生成器,用来生成含有主键key的类，记录类 以及查询Example类
                targetPackage     指定生成的model生成所在的包名
                targetProject     指定在该项目下所在的路径
            -->
            <!--<javaModelGenerator targetPackage="com.mmall.pojo" targetProject=".\src\main\java">-->
            <javaModelGenerator targetPackage="com.mmall.pojo" targetProject="./src/main/java">
                <!-- 是否允许子包，即targetPackage.schemaName.tableName -->
                <property name="enableSubPackages" value="false"/>
                <!-- 是否对model添加 构造函数 -->
                <property name="constructorBased" value="true"/>
                <!-- 是否对类CHAR类型的列的数据进行trim操作 -->
                <property name="trimStrings" value="true"/>
                <!-- 建立的Model对象是否 不可改变  即生成的Model对象不会有 setter方法，只有构造方法 -->
                <property name="immutable" value="false"/>
            </javaModelGenerator>
    
            <!--mapper映射文件生成所在的目录 为每一个数据库的表生成对应的SqlMap文件 -->
            <!--<sqlMapGenerator targetPackage="mappers" targetProject=".\src\main\resources">-->
            <sqlMapGenerator targetPackage="mappers" targetProject="./src/main/resources">
                <property name="enableSubPackages" value="false"/>
            </sqlMapGenerator>
    
            <!-- 客户端代码，生成易于使用的针对Model对象和XML配置文件 的代码
                    type="ANNOTATEDMAPPER",生成Java Model 和基于注解的Mapper对象
                    type="MIXEDMAPPER",生成基于注解的Java Model 和相应的Mapper对象
                    type="XMLMAPPER",生成SQLMap XML文件和独立的Mapper接口
            -->
    
            <!-- targetPackage：mapper接口dao生成的位置 -->
            <!--<javaClientGenerator type="XMLMAPPER" targetPackage="com.mmall.dao" targetProject=".\src\main\java">-->
            <javaClientGenerator type="XMLMAPPER" targetPackage="com.mmall.dao" targetProject="./src/main/java">
                <!-- enableSubPackages:是否让schema作为包的后缀 -->
                <property name="enableSubPackages" value="false" />
            </javaClientGenerator>
    
    
            <table tableName="mmall_shipping" domainObjectName="Shipping" enableCountByExample="false" enableUpdateByExample="false" enableDeleteByExample="false" enableSelectByExample="false" selectByExampleQueryId="false"></table>
            <table tableName="mmall_cart" domainObjectName="Cart" enableCountByExample="false" enableUpdateByExample="false" enableDeleteByExample="false" enableSelectByExample="false" selectByExampleQueryId="false"></table>
            <table tableName="mmall_cart_item" domainObjectName="CartItem" enableCountByExample="false" enableUpdateByExample="false" enableDeleteByExample="false" enableSelectByExample="false" selectByExampleQueryId="false"></table>
            <table tableName="mmall_category" domainObjectName="Category" enableCountByExample="false" enableUpdateByExample="false" enableDeleteByExample="false" enableSelectByExample="false" selectByExampleQueryId="false"></table>
            <table tableName="mmall_order" domainObjectName="Order" enableCountByExample="false" enableUpdateByExample="false" enableDeleteByExample="false" enableSelectByExample="false" selectByExampleQueryId="false"></table>
            <table tableName="mmall_order_item" domainObjectName="OrderItem" enableCountByExample="false" enableUpdateByExample="false" enableDeleteByExample="false" enableSelectByExample="false" selectByExampleQueryId="false"></table>
            <table tableName="mmall_pay_info" domainObjectName="PayInfo" enableCountByExample="false" enableUpdateByExample="false" enableDeleteByExample="false" enableSelectByExample="false" selectByExampleQueryId="false"></table>
            <table tableName="mmall_product" domainObjectName="Product" enableCountByExample="false" enableUpdateByExample="false" enableDeleteByExample="false" enableSelectByExample="false" selectByExampleQueryId="false">
                <columnOverride column="detail" jdbcType="VARCHAR" />
                <columnOverride column="sub_images" jdbcType="VARCHAR" />
            </table>
            <table tableName="mmall_user" domainObjectName="User" enableCountByExample="false" enableUpdateByExample="false" enableDeleteByExample="false" enableSelectByExample="false" selectByExampleQueryId="false"></table>
    
    
            <!-- geelynote mybatis插件的搭建 -->
        </context>
    </generatorConfiguration>
    
    Mybatis-plugin插件
    提供Mapper接口与配置文件中对应SQL的导航
    编辑XML文件时自动补全
    自动检查Mapper XML文件中ID冲突
    自动检查Mapper XML文件中错误的属性值
    等等
    
    Mybatis-PageHelper


**用户模块：**

    1、功能介绍
    2、学习目标
    3、数据表设计
    4、接口设计

**功能介绍：**

    登录、用户名验证、注册、忘记密码、提交问题答案、重置密码、获取用户信息、更新用户信息、退出登录
    
    学习目标：
        横向越权。纵向越权安全漏洞
        MD5明文加密及增加salt值
        Guava缓存的使用
        高复用服务响应对象的设计思想及抽象封装
        Mybatis-plugin的使用技巧
        session的使用
        方法局部演进
        
        横向越权：攻击者尝试访问与它拥有相同权限的用户资源
        纵向越权：低级别攻击者尝试访问高级别用户资源
        
    
        
    
        
        


