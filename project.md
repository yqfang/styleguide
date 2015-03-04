AngularJs项目目录规范
=======================

此为前端开发团队遵循和约定的**AngularJs项目目录规范**，意在实现项目目录结构的一致性。

## 说明
文档中使用的关键字"MUST","MUST NOT","REQUIRED","SHALL","SHALL
NOT","SHOULD","SHOULD NOT","RECOMMENDED","MAY"和"OPTIONAL"在[RFC2119](http://oss.org.cn/man/develop/rfc/RFC2119.txt)中被说明。

**还未定稿，对规范中提及的点有不赞同的欢迎[提出 issues ](https://github.com/yqfang/styleguide/issues/new)(请添加`目录规范`标签)讨论。**

## 目录规范

参考angular官方项目: [angular-phonecat](https://github.com/angular/angular-phonecat)
项目的基本目录结构为：

```
 / # which is the root for the project 
 |-- app # which is the web root in develop period
      |-- lib # which is root for the bower_components and the user-defined components
      |-- resources  # which is the static resources
              |-- css 
              |-- less
              |-- img
      |-- modules # where you should concentrate on coding 
           |-- common # where to put the common directives, fliters, services..
           |-- others # where to put bussiness-oriented modules, and where you will refactor again and again.
                 |-- main.js # where to define the submodules and the routes for the module
                 |-- controllers # where to put controllers
                 |-- services 
                 |-- directives
                 |-- fliter # I don't think there exist some bussiness-related fliters, so leave it or not 
                 |-- views # where to put html partials like the templates for dialogs
      |-- index.html # which is the home page
 |-- dist # which is the webRoot for publish
 |-- script # where to put some publish-related scripts some like fis.conf or gulp.conf
 |-- test # where to put you test cases
 |-- README.md  # where to briefly introduce your project
```

### README.md

每个项目都必须"MUST"包含一个`README.md`文件，此文件中应当"SHOULD"概要描述此项目的功能和特点等信息。

### dist

dist 作为项目发布目录，所有编译生成、提供给用户使用的文件应当"SHOULD"存放在此目录, 关于项目发布的配置说明请参考
[AngularJs 项目发布说明](./angular-publish.md)。

发布目录不必提交。

### modules

modules 作为所有业务模块的路口，在开发和代码重构过程中文件的改变可能会很大。
