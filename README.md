# 개발환경  

--- 

* JDK: 11  
* DB: mysql  
* mybatis  
* view: JSP

---
## [IntelliJ] 웹 프로젝트 생성
1. File [New Project] 버튼 클릭
  1) New Project  
  	• Name:spring-setting  
	• Location:C:\Dev\workspace  
	• JDK:11  
	• Catalog:  
	• Archetype:org.apache.maven.archetypes:maven-archetype-webapp  
	• GroupId:org.example  
	• ArtifactId:spring-setting  
  2) Create 버튼 클릭  
   [참고] 프로젝트 이름  
   • 첫번째 방법 소문자 + 카멜케이스 (예시: springBootProject, springMvcApp)  
   • 두번째 방법 소문자 + 하이픈 (예시:spring-boot-project, spring-mvc-app)  

2. Setting 설정(File>Setting)  
1) Editor > File Encodings > UTF-8  
2) Editor > Build Tools > Maven >  

3. Spring MVC 구조 확인  

  1) src/web/WEB-INF/  
   • applicationContext.xml :	ApplicationContext 생성 시 필요한 설정정보를 담은 파일    
   • dispatcher-server.xml : HTTP 프로토콜로 들어오는 모든 요청을 가장 먼저 받아  
     적합한 컨트롤러에 위임해주는 프론트 컨트롤러(Front Controller)  
   • web.xml :	서블릿 맵핑 되는 방법 ,인증이 필요한 URL 등의 정보  
    * applicationContext.xml → root-context.xml  으로 리팩토링  
    * dispatcher-server.xml → servlet-context.xml 으로 리팩토링  
    * webapp → web 으로 리팩토링 하면 톰캣 기동의 문제 

  2) src/main/밑에 java 폴더 선택 후 생성  
  3) java 폴더에 package 생성    
    - GroupId + ArtifactId (예시 package org.spring.basics )  
    - package org.spring.basics.controller   
    - HomeController 생성  
    - <context:component-scan base-package="**org.spring.basics**" />  
  4) src/web/WEB-INF/밑에 views 폴더 생성  
    - index.jsp 생성  
  5) {webappRoot}/ 밑에 resources 폴더 생성   
    <resources mapping="/resources/**" location="/resources/"/>   

4. pom.xml 수정  

5. File → Project Stucture  
  1) Modules  
     web/WEB-INF/views  
  2) Facets  
     • Spring
       ◦ application context  
       ◦ appServlet servlet context  
     • Web  
  2) Artifacts  
   • 프로젝트명 : war exploded」  
    - web/WEB-INF/lib 밑에 Spring-버전.RELEASE.jar,   
      Spring MVC-버전.RELEASE.jar 라이브러리가 추가  

6. Tomcat  
1) Run → Edit Configuration  
   ① Run → Edit Configuration  
   ② Ren / Debug Configurations 팝업창 「+」 버튼  
   ③ Tomcat Server > Local 선택  
2) Tomcat Server 설정  
   ① Configuration  
   ② Tomcat Home 선택  
   ③ Open Browser 선택  
   ④ VM options :-Duser.language=en -Duser.region=us  
   ⑤ JRE 지정  
   ⑥ HTTP port  
3) Tomcat Deployment 설정  
   ① Deployment  
   ② 「+」 버튼을 클릭하여 Artifact를 추가한다.  
   ③ 프로젝트명 : war exploded」  
   ④ Application Context  
** / 로 하면  
   http://localhost:8080/main.sp  
   Origin 서버가 대상 리소스를 위한 현재의 representation을 찾지 못했거나, 그것이 존재하는지를 밝히려 하지 않습니다.
--> 해결
   /basics
   http://localhost:8080/basics/

---
 git : https://github.com/jeongwo2/spring-basics.git

create a new repository on the command line  

echo "# spring-basics" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/jeongwo2/spring-basics.git
git push -u origin main

push an existing repository from the command line  
git remote add origin https://github.com/jeongwo2/spring-basics.git
git branch -M main
git push -u origin main  
