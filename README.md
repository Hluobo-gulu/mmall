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
    使用mybatis-generator只需要简单的配置就能完成，这里简述一下开发步骤。
    
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
        
    
        
        


