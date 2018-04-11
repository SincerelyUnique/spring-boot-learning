## Spring Guides - Validating Form Input

### 说明

1. 该项目展示了Spring的表单验证；
2. 在实体属性上添加validation，当请求携带的参数通过controller接口进来时直接通过@Valid注解做验证；

### 异常

```
2018-04-11 09:55:46.167 ERROR 16720 --- [nio-8080-exec-2] org.thymeleaf.TemplateEngine             : [THYMELEAF][http-nio-8080-exec-2] Exception processing template "form": Error during execution of processor 'org.thymeleaf.spring5.processor.SpringInputGeneralFieldTagProcessor' (template: "form" - line 13, col 36)

org.thymeleaf.exceptions.TemplateProcessingException: Error during execution of processor 'org.thymeleaf.spring5.processor.SpringInputGeneralFieldTagProcessor' (template: "form" - line 13, col 36)
	at org.thymeleaf.processor.element.AbstractAttributeTagProcessor.doProcess(AbstractAttributeTagProcessor.java:117) ~[thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.processor.element.AbstractElementTagProcessor.process(AbstractElementTagProcessor.java:95) ~[thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.util.ProcessorConfigurationUtils$ElementTagProcessorWrapper.process(ProcessorConfigurationUtils.java:633) ~[thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.engine.ProcessorTemplateHandler.handleStandaloneElement(ProcessorTemplateHandler.java:918) ~[thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.engine.StandaloneElementTag.beHandled(StandaloneElementTag.java:228) ~[thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.engine.TemplateModel.process(TemplateModel.java:136) ~[thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.engine.TemplateManager.parseAndProcess(TemplateManager.java:661) ~[thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.TemplateEngine.process(TemplateEngine.java:1098) [thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.TemplateEngine.process(TemplateEngine.java:1072) [thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.spring5.view.ThymeleafView.renderFragment(ThymeleafView.java:354) [thymeleaf-spring5-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.spring5.view.ThymeleafView.render(ThymeleafView.java:187) [thymeleaf-spring5-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.springframework.web.servlet.DispatcherServlet.render(DispatcherServlet.java:1325) [spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.servlet.DispatcherServlet.processDispatchResult(DispatcherServlet.java:1069) [spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.servlet.DispatcherServlet.doDispatch(DispatcherServlet.java:1008) [spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.servlet.DispatcherServlet.doService(DispatcherServlet.java:925) [spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.servlet.FrameworkServlet.processRequest(FrameworkServlet.java:974) [spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.servlet.FrameworkServlet.doGet(FrameworkServlet.java:866) [spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:635) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.springframework.web.servlet.FrameworkServlet.service(FrameworkServlet.java:851) [spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:742) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:231) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.tomcat.websocket.server.WsFilter.doFilter(WsFilter.java:52) [tomcat-embed-websocket-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.springframework.web.filter.RequestContextFilter.doFilterInternal(RequestContextFilter.java:99) [spring-web-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:107) [spring-web-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.springframework.web.filter.HttpPutFormContentFilter.doFilterInternal(HttpPutFormContentFilter.java:109) [spring-web-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:107) [spring-web-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.springframework.web.filter.HiddenHttpMethodFilter.doFilterInternal(HiddenHttpMethodFilter.java:81) [spring-web-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:107) [spring-web-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.springframework.web.filter.CharacterEncodingFilter.doFilterInternal(CharacterEncodingFilter.java:200) [spring-web-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:107) [spring-web-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.StandardWrapperValve.invoke(StandardWrapperValve.java:198) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.StandardContextValve.invoke(StandardContextValve.java:96) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.authenticator.AuthenticatorBase.invoke(AuthenticatorBase.java:496) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.StandardHostValve.invoke(StandardHostValve.java:140) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.valves.ErrorReportValve.invoke(ErrorReportValve.java:81) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.StandardEngineValve.invoke(StandardEngineValve.java:87) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.connector.CoyoteAdapter.service(CoyoteAdapter.java:342) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.coyote.http11.Http11Processor.service(Http11Processor.java:803) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.coyote.AbstractProcessorLight.process(AbstractProcessorLight.java:66) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.coyote.AbstractProtocol$ConnectionHandler.process(AbstractProtocol.java:790) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.tomcat.util.net.NioEndpoint$SocketProcessor.doRun(NioEndpoint.java:1459) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.tomcat.util.net.SocketProcessorBase.run(SocketProcessorBase.java:49) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142) [na:1.8.0_112]
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617) [na:1.8.0_112]
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at java.lang.Thread.run(Thread.java:745) [na:1.8.0_112]
Caused by: org.springframework.beans.NotReadablePropertyException: Invalid property 'name' of bean class [com.example.demo.model.PersonForm]: Bean property 'name' is not readable or has an invalid getter method: Does the return type of the getter match the parameter type of the setter?
	at org.springframework.beans.AbstractNestablePropertyAccessor.getPropertyValue(AbstractNestablePropertyAccessor.java:622) ~[spring-beans-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.beans.AbstractNestablePropertyAccessor.getPropertyValue(AbstractNestablePropertyAccessor.java:612) ~[spring-beans-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.validation.AbstractPropertyBindingResult.getActualFieldValue(AbstractPropertyBindingResult.java:104) ~[spring-context-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.validation.AbstractBindingResult.getFieldValue(AbstractBindingResult.java:228) ~[spring-context-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.servlet.support.BindStatus.<init>(BindStatus.java:129) ~[spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.servlet.support.RequestContext.getBindStatus(RequestContext.java:903) ~[spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.thymeleaf.spring5.context.webmvc.SpringWebMvcThymeleafRequestContext.getBindStatus(SpringWebMvcThymeleafRequestContext.java:227) ~[thymeleaf-spring5-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.spring5.util.FieldUtils.getBindStatusFromParsedExpression(FieldUtils.java:305) ~[thymeleaf-spring5-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.spring5.util.FieldUtils.getBindStatus(FieldUtils.java:252) ~[thymeleaf-spring5-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.spring5.util.FieldUtils.getBindStatus(FieldUtils.java:226) ~[thymeleaf-spring5-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.spring5.processor.AbstractSpringFieldTagProcessor.doProcess(AbstractSpringFieldTagProcessor.java:174) ~[thymeleaf-spring5-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.processor.element.AbstractAttributeTagProcessor.doProcess(AbstractAttributeTagProcessor.java:74) ~[thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	... 56 common frames omitted

2018-04-11 09:55:46.172 ERROR 16720 --- [nio-8080-exec-2] o.a.c.c.C.[.[.[/].[dispatcherServlet]    : Servlet.service() for servlet [dispatcherServlet] in context with path [] threw exception [Request processing failed; nested exception is org.thymeleaf.exceptions.TemplateProcessingException: Error during execution of processor 'org.thymeleaf.spring5.processor.SpringInputGeneralFieldTagProcessor' (template: "form" - line 13, col 36)] with root cause

org.springframework.beans.NotReadablePropertyException: Invalid property 'name' of bean class [com.example.demo.model.PersonForm]: Bean property 'name' is not readable or has an invalid getter method: Does the return type of the getter match the parameter type of the setter?
	at org.springframework.beans.AbstractNestablePropertyAccessor.getPropertyValue(AbstractNestablePropertyAccessor.java:622) ~[spring-beans-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.beans.AbstractNestablePropertyAccessor.getPropertyValue(AbstractNestablePropertyAccessor.java:612) ~[spring-beans-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.validation.AbstractPropertyBindingResult.getActualFieldValue(AbstractPropertyBindingResult.java:104) ~[spring-context-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.validation.AbstractBindingResult.getFieldValue(AbstractBindingResult.java:228) ~[spring-context-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.servlet.support.BindStatus.<init>(BindStatus.java:129) ~[spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.servlet.support.RequestContext.getBindStatus(RequestContext.java:903) ~[spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.thymeleaf.spring5.context.webmvc.SpringWebMvcThymeleafRequestContext.getBindStatus(SpringWebMvcThymeleafRequestContext.java:227) ~[thymeleaf-spring5-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.spring5.util.FieldUtils.getBindStatusFromParsedExpression(FieldUtils.java:305) ~[thymeleaf-spring5-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.spring5.util.FieldUtils.getBindStatus(FieldUtils.java:252) ~[thymeleaf-spring5-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.spring5.util.FieldUtils.getBindStatus(FieldUtils.java:226) ~[thymeleaf-spring5-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.spring5.processor.AbstractSpringFieldTagProcessor.doProcess(AbstractSpringFieldTagProcessor.java:174) ~[thymeleaf-spring5-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.processor.element.AbstractAttributeTagProcessor.doProcess(AbstractAttributeTagProcessor.java:74) ~[thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.processor.element.AbstractElementTagProcessor.process(AbstractElementTagProcessor.java:95) ~[thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.util.ProcessorConfigurationUtils$ElementTagProcessorWrapper.process(ProcessorConfigurationUtils.java:633) ~[thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.engine.ProcessorTemplateHandler.handleStandaloneElement(ProcessorTemplateHandler.java:918) ~[thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.engine.StandaloneElementTag.beHandled(StandaloneElementTag.java:228) ~[thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.engine.TemplateModel.process(TemplateModel.java:136) ~[thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.engine.TemplateManager.parseAndProcess(TemplateManager.java:661) ~[thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.TemplateEngine.process(TemplateEngine.java:1098) ~[thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.TemplateEngine.process(TemplateEngine.java:1072) ~[thymeleaf-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.spring5.view.ThymeleafView.renderFragment(ThymeleafView.java:354) ~[thymeleaf-spring5-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.thymeleaf.spring5.view.ThymeleafView.render(ThymeleafView.java:187) ~[thymeleaf-spring5-3.0.9.RELEASE.jar:3.0.9.RELEASE]
	at org.springframework.web.servlet.DispatcherServlet.render(DispatcherServlet.java:1325) ~[spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.servlet.DispatcherServlet.processDispatchResult(DispatcherServlet.java:1069) ~[spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.servlet.DispatcherServlet.doDispatch(DispatcherServlet.java:1008) ~[spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.servlet.DispatcherServlet.doService(DispatcherServlet.java:925) ~[spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.servlet.FrameworkServlet.processRequest(FrameworkServlet.java:974) ~[spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.servlet.FrameworkServlet.doGet(FrameworkServlet.java:866) ~[spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:635) ~[tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.springframework.web.servlet.FrameworkServlet.service(FrameworkServlet.java:851) ~[spring-webmvc-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:742) ~[tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:231) ~[tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) ~[tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.tomcat.websocket.server.WsFilter.doFilter(WsFilter.java:52) ~[tomcat-embed-websocket-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193) ~[tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) ~[tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.springframework.web.filter.RequestContextFilter.doFilterInternal(RequestContextFilter.java:99) ~[spring-web-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:107) ~[spring-web-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193) ~[tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) ~[tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.springframework.web.filter.HttpPutFormContentFilter.doFilterInternal(HttpPutFormContentFilter.java:109) ~[spring-web-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:107) ~[spring-web-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193) ~[tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) ~[tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.springframework.web.filter.HiddenHttpMethodFilter.doFilterInternal(HiddenHttpMethodFilter.java:81) ~[spring-web-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:107) ~[spring-web-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193) ~[tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) ~[tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.springframework.web.filter.CharacterEncodingFilter.doFilterInternal(CharacterEncodingFilter.java:200) ~[spring-web-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:107) ~[spring-web-5.0.5.RELEASE.jar:5.0.5.RELEASE]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193) ~[tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) ~[tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.StandardWrapperValve.invoke(StandardWrapperValve.java:198) ~[tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.StandardContextValve.invoke(StandardContextValve.java:96) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.authenticator.AuthenticatorBase.invoke(AuthenticatorBase.java:496) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.StandardHostValve.invoke(StandardHostValve.java:140) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.valves.ErrorReportValve.invoke(ErrorReportValve.java:81) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.core.StandardEngineValve.invoke(StandardEngineValve.java:87) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.catalina.connector.CoyoteAdapter.service(CoyoteAdapter.java:342) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.coyote.http11.Http11Processor.service(Http11Processor.java:803) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.coyote.AbstractProcessorLight.process(AbstractProcessorLight.java:66) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.coyote.AbstractProtocol$ConnectionHandler.process(AbstractProtocol.java:790) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.tomcat.util.net.NioEndpoint$SocketProcessor.doRun(NioEndpoint.java:1459) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at org.apache.tomcat.util.net.SocketProcessorBase.run(SocketProcessorBase.java:49) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142) [na:1.8.0_112]
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617) [na:1.8.0_112]
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61) [tomcat-embed-core-8.5.29.jar:8.5.29]
	at java.lang.Thread.run(Thread.java:745) [na:1.8.0_112]

```

该异常是因为在构建实体类时忘记添加setter，getter方法了，我这里是忘记写lombok注解，补充上lombok注解后运行即可

### 参考

https://spring.io/guides/gs/validating-form-input/ （Spring Guides）

https://github.com/spring-guides/gs-validating-form-input （Source Code）

https://stackoverflow.com/questions/45618278/notreadablepropertyexception-invalid-property-names-of-bean-class （异常处理）