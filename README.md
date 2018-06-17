### SpringBoot 1.5.8 + Lombok
[![Build Status](https://www.travis-ci.org/DemoOfBug/springboot-maven-archetype.svg?branch=master)](https://www.travis-ci.org/DemoOfBug/springboot-maven-archetype) 

> 脚手架功能  

- 设置默认编码为UTF-8
- 版本为JDK 1.8
- SpringBoot 1.5.8、Lombok

>安装方式    

1. 安装jar到本地仓库  

```mvn install```

2. 运行  
- 一、命令行方式  
```mvn archetype:generate -DarchetypeGroupId=org.springframework.boot -DarchetypeArtifactId=spring-boot-maven-archetype -DarchetypeVersion=1.0 -DinteractiveMode=false -DarchetypeCatalog=local -DgroupId=com.github -DartifactId=sample-boot -Dversion=1.0```  
-二、 eclipse配置脚手架  
Windows -> Preferences -> Maven ->Archetypes -> Add Local Catalog Archetype 选中工程中archetype-catalog-local.xml  
创建maven工程时选spring-boot-maven-archetype,即可  

> 生成Maven工程，Pom文件  

``` 
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<artifactId>samples-springboot</artifactId>
	<groupId>com.github</groupId>
	<version>1.0</version>

	<properties>
		<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
		<project.build.version>1.0</project.build.version>
		<project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
		<java.version>1.8</java.version>
		<spring.boot.version>1.5.8.RELEASE</spring.boot.version>
	</properties>

	<dependencyManagement>
		<dependencies>
			<dependency>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-dependencies</artifactId>
				<version>${spring.boot.version}</version>
				<type>pom</type>
				<scope>import</scope>
			</dependency>
		</dependencies>
	</dependencyManagement>

	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
			<optional>true</optional>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-devtools</artifactId>
			<optional>true</optional>
		</dependency>

		<!-- lombok -->
		<dependency>
			<groupId>org.projectlombok</groupId>
			<artifactId>lombok</artifactId>
		</dependency>

		<!-- test -->
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
		<pluginManagement>
			<plugins>
				<plugin>
					<groupId>org.apache.maven.plugins</groupId>
					<artifactId>maven-compiler-plugin</artifactId>
					<version>2.3.2</version>
					<configuration>
						<source>${java.version}</source>
						<target>${java.version}</target>
						<showWarnings>true</showWarnings>
						<encoding>${project.build.sourceEncoding}</encoding>
					</configuration>
				</plugin>

				<!-- resource插件, 设定编码 -->
				<plugin>
					<groupId>org.apache.maven.plugins</groupId>
					<artifactId>maven-resources-plugin</artifactId>
					<version>2.4.3</version>
					<configuration>
						<encoding>${project.build.sourceEncoding}</encoding>
					</configuration>
				</plugin>

				<plugin>
					<groupId>org.apache.maven.plugins</groupId>
					<artifactId>maven-surefire-plugin</artifactId>
					<version>2.4.2</version>
					<configuration>
						<skipTests>true</skipTests>
					</configuration>
				</plugin>
			</plugins>
		</pluginManagement>
	</build>
</project>
```  
