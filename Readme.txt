https://howtodoinjava.com/spring-restful/custom-token-auth-example/
 
 
1. 用tomcat部署, war 或者 exploded都可以，都是要写到/webapp下
2. 如果load-on-startup不为1，就要收到第一个restful请求的时候才初始化这个servlet “rest”， 这个servelet映射/api/rest/*
2.  HTTP GET http://localhost:8080/SpringRestExample/api/rest/employee-management/employees/
 
在header要带上
AUTH_API_KEY
才可以访问
 
参见/scratch目录下的http请求文件 
createEmployee
findAllEmployee
 
3. 已经部署H2， 调用上一步的createEmployee才会有记录，
 然后再执行上述http请求findAllEmployee就可以有返回值
 
 
问题：
在idea用db 工具连接到h2（jdbc:h2:mem:testdb），但是查不到tbl_employee
好像每次close session都删除表一样
