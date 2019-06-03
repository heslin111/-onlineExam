# 在线考试系统

csdn博客https://blog.csdn.net/Leon_Theprofessional/article/details/90750313

项目后台采用SSM框架整合，数据库版本是mysql5.1.37,使用maven管理jar包，以及对jdbc文件配置的账号密码进行了加密处理。前台页面使用的是jsp，使用jstl标签进行数据处理。目前实现功能：
  1.登录注册
  2.学生做题：
    后台从数据库中随机选取20道题，然后将题目存于session中，前台从session拿到题目，提交后将选择结果提交到后台，后台通过session拿到原有的题目对象，getSubjectAnswer获取正确答案，同前台传来的学生选择的答案进行比较，如果相符，则总分加五分。
  3.老师对于题目的增删改查操作。
  4.老师对于学生账号一系列操作。
  5.使用filter拦截没有操作权限的用户，通过在类名前面加上Requestmapping("/xxx")，配置过滤器，访问这个类时候会先进入filter,因为在登录时候往session中存放了用户登录的对象，如果在filter中，这个对象为空，说明没有登录，拒绝访问相应接口，提示用户未登录。
  
