---
title: Spring Internals Note
date: 2024-07-10 17:52:37
tags:
---

# Qn to figure out

1. what's the relationship of AspectJ and AOP? AspectJ is the impl? AOP is interface or spec? 
   - impl via JVM 動態代理 + CGLIB?
   - AOP 攔截器？

2. SpringMVC: a good pattern for web app 
   - DispatcherServlet impl MVC pattern
   - web req 的攔截，分發，處理，ModelAndView 的數據返回

3. ACEGI -> Spring Security 
4. Spring JDBC / ORM 
  - Spring encapsulated JDBC -> JdbcTemplate for basic ops to DB (CRUD I suppose)
  - HibernateTemplate
5. Spring Trnx 
  - 聲明式事務處理？
  - impl via AOP
  - can conf use which trnx mechanism
  - decouple with business logic 
6. OSGi? 




# IoC Container 
- `ApplicationContext` is a powerful impl of it?
- BeanFactory (interface)