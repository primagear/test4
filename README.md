	# test4
	java path&URL methods

	public void doGet(HttpServletRequest request, HttpServletResponse response)
	throws ServletException, IOException {

	response.setContentType("text/html");
	PrintWriter out = response.getWriter();
		
	//返回工程名部分    context path is : /day06
	String contxtpath =  request.getContextPath();
	out.println("context path is:" + contxtpath );
	out.println("<br/>");
		
	//返回资源路径    resource URL is : jndi:localhost/day06/
	URL resourURL =  this.getServletContext().getResource("/");
	out.println("resource URL is:" + resourURL);
	out.println("<br/>");
		
	//返回    resourPathsURL is : [/index.jsp, /WEB-INF/, /META-INF/]
	Set resourPathsURL =  this.getServletContext().getResourcePaths("/");
	out.println("resourPathsURL is:" + resourPathsURL);
	out.println("<br/>");
		
	//返回实际路径    real path is : D:\apache-tomcat-7.0.78\webapps\day06\ccc
	String realpath =  request.getRealPath("/");
	out.println("real path is:" + realpath );
	out.println("<br/>");
		
	//返回除去host的路径    requestURI is : /day06/ccc
	String requestURI =  request.getRequestURI();
	out.println("requestURI is:" + requestURI );
	out.println("<br/>");
		 
	//返回全部路径    requestURL is : http://localhost:8080/day06/ccc
	StringBuffer requestURL =  request.getRequestURL();
	out.println("requestURL is:" + requestURL );
	out.println("<br/>");
		
	//返回除去host和工程名部分的路径    ServletPath is : /ccc
	String servletpath =  request.getServletPath();
	out.println("ServletPath is:" + servletpath);
	out.println("<br/>");
		 
	out.flush();
	out.close();
