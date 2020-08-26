
自定义的图形验证码

ImgCodeServlet用法:

    /**
     * 添加配置Servlet,使用默认的session的key,验证码,url http://127.0.0.1:8080/imgCode
     * @param
     * @作者 田应平
     * @QQ 444141300
     * @创建时间 2019/7/13 14:05
    */
    @Bean
    public ServletRegistrationBean servletRegistration() {
        final ServletRegistrationBean registration = new ServletRegistrationBean(new ImgCodeServlet());
        registration.addUrlMappings("/imgCode");
        return registration;
    }
    或
    /**
     * 添加配置Servlet,指定session的key,验证码,url http://127.0.0.1:8080/imgCode
     * @param
     * @作者 田应平
     * @QQ 444141300
     * @创建时间 2019/7/13 14:05
    */
    @Bean
    public ServletRegistrationBean servletRegistration() {
        final ServletRegistrationBean registration = new ServletRegistrationBean(new ImgCodeServlet("captcha"));
        registration.addUrlMappings("/imgCode");
        return registration;
    }

基于算术生成图形验证码ImgCode用法:

    //指定session的key http://127.0.0.1:8080/captcha
    @Bean
    public ServletRegistrationBean<HttpServlet> captcha() {
        return new ServletRegistrationBean(new ImgCode("captcha"),"/captcha");
    }
    或
    //使用默认的session的key http://127.0.0.1:8080/captcha
    @Bean
    public ServletRegistrationBean<HttpServlet> captcha() {
        return new ServletRegistrationBean(new ImgCode(),"/captcha");
    }