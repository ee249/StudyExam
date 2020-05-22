## R과 Java를 이용해서 지역 추출

#### 비슷한 문제

- 준비 작업

1. Rstudio에 가서 install.packages("Rserve") 를 설치한다.
2. java eclipse에 mvc project에 있는 pom.xml에 밑에 있는 코드를 추가하다.

```xml
	<dependency>
			<groupId>com.github.lucarosellini.rJava</groupId>
			<artifactId>JRIEngine</artifactId>
			<version>0.9-7</version>
		</dependency>
		<dependency>
			<groupId>net.rforge</groupId>
			<artifactId>Rserve</artifactId>
			<version>0.6-8.1</version>
		</dependency>
```

3. 

   1-1) C:\Users\student\Documents\R\win-library\3.6\Rserve\libs\x64(윈도우10)

   1-2) C:\Program Files\R\R-3.6.1\library\Rserve\libs\x64(윈도우7)

   \- 1-1), 1-2) 중 본인 컴퓨터에 맞는 곳에 들어가서 모두 복사한 후

   2) C:\Program Files\R\R-xxxx\bin\x64 디렉토리에 들어가서 붙여 넣는다.

   3) cmd 창을 띄우고 C:\Program Files\R\R-xxxx\bin\x64 디렉토리에 들어간다.

   4) Rserve --RS-encoding utf8을 수행시킨다.



- OnePersonController

```java
package edu.spring.redu;

import java.io.File;

import javax.servlet.http.HttpServletRequest;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.servlet.ModelAndView;

import rtest.OnePersonService;

@Controller
public class OnePersonController {
	
	@Autowired
	OnePersonService one;
	
	@RequestMapping("/map7")
	public ModelAndView get1(HttpServletRequest req) {
		ModelAndView mav = new ModelAndView();
		String real_path1 = req.getSession().getServletContext().getRealPath("/"); // 톰캣이 실제로 사용하는 path를 뽑을 수 있다.
		System.out.println(real_path1); // 리얼 주소
	    real_path1 = real_path1.replace("\\", "/");
	    System.out.println(real_path1);		
		File f = new File(real_path1+"/resources/abc"); // 실제로 톰캣이 사용하는 폴더를 만드는 것
		if(!f.exists()) {
			f.mkdir();
		}
		String guname = req.getParameter("guname");
		System.out.print(guname);
		String result = one.returnLeaflet(real_path1+"/resources/abc", guname);
		System.out.print(result);
		mav.addObject("leafletChartName1", "http://localhost:8000/redu/resources/abc/"+result);
		mav.setViewName("oneView");
		return mav;
	}	
}

```



- OnePersonService

```java
package rtest;

import org.rosuda.REngine.Rserve.RConnection;
import org.springframework.stereotype.Service;

@Service
public class OnePersonService {
	public String returnLeaflet(String path, String guname)  {
		RConnection r = null;
		String retStr = "";
		try {
			r = new RConnection(); 
			r.eval("setwd('c:/younggi/Rstudy');");
			r.eval("library(Kormaps);");
			r.eval("library(dplyr);");
			r.eval("library(leaflet);");
			r.eval("library(htmlwidgets);");
			r.eval("k2 <- NULL;" + 
					"k3 <- NULL;");
			r.eval("Encoding(names(korpopmap2)) <- 'UTF-8';" + 
					"Encoding(names(korpopmap3)) <- 'UTF-8';" +  
					"Encoding(korpopmap2@data$name)<-'UTF-8';" + 
					"Encoding(korpopmap2@data$행정구역별_읍면동)<-'UTF-8';" + 
					"Encoding(korpopmap3@data$name)<-'UTF-8';" + 
					"Encoding(korpopmap3@data$행정구역별_읍면동)<-'UTF-8';");
			r.eval("k2 <- korpopmap2;" + 
					"k3 <- korpopmap3;");
			r.eval("guname <- iconv('"+guname +"', from='CP949', to='UTF-8');");
			r.eval("gucode <- k2@data[k2@data$name == guname, \"code.data\"];" + 
					"pattern <- paste0('^', gucode);");
			r.eval("k3@polygons<-k3@polygons[grep(pattern, k3@data$code.data)];" + 
					"k3@data<-k3@data[grep(pattern, k3@data$code.data),];");
			
			r.eval("DONG <- read.csv(\"data/one.csv\");"
					+ "k3@data$name<-gsub('·','',k3@data$name);" + 
					"colnames(DONG)<-c('구별','name','일인가구');");
			r.eval("dong <- DONG %>%filter(구별==guname);");
			r.eval("popup1 <- paste0(dong$name,'<br> 1인가구 : ',dong$일인가구, '건');" + 
					"palette1<-colorNumeric(palette = 'Oranges', domain = dong$일인가구);" + 
					"k3@data<-merge(k3@data,dong,by.x='name',sort=FALSE);" + 
					"mymap <- k3@data;");
			r.eval("map7 <- NULL;" + 
					"map7<-leaflet(k3) %>% " + 
					"  addTiles() %>% " + 
					"  setView(lat=37.52711, lng=126.987517, zoom=12) %>%" + 
					"  addPolygons(stroke =FALSE," + 
					"              fillOpacity = .7," + 
					"              popup = popup1," + 
					"              color = ~palette1(mymap$일인가구)) %>% " + 
					"  addLegend( values = ~mymap$일인가구, " + 
					"             pal = palette1 , " + 
					"             title = '인구수', " + 
					"             opacity = 1);");
			String fileName = path + "/index.html";
			r.eval("saveWidget(map7,'"+fileName+"',  selfcontained = F);");	        
			retStr = r.eval("'index.html'").asString();
		} catch (Exception e) {
			System.out.println(e);
			e.printStackTrace();
		} finally {
			r.close(); 
		}
		return retStr;
	}	
}

```



- oneView.jsp

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
	<h1>문제</h1> 
<hr>
<iframe src="${leafletChartName1}" width="100%" height=500></iframe> 
</body>
</html>
```



\- http://localhost:8000/redu/map7?guname=구로구 이렇게 들어가면 된다.