# spring-boot-crud

#dependencias
#mysql
#vagrant
#java
#spring boot

# 1)Criar aplicacao spring-boot de crud


# 2)Adicionar o actuator

pom.xml

<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-actuator</artifactId>
		</dependency>

		<dependency>
			<groupId>org.jolokia</groupId>
			<artifactId>jolokia-core</artifactId>
		</dependency>


	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
				<executions>
					<execution>
						<goals>
							<goal>build-info</goal>
							<goal>repackage</goal>
						</goals>
						<configuration>
							<additionalProperties>
								<java.target>${maven.compiler.target}</java.target>
								<time>${maven.build.timestamp}</time>
							</additionalProperties>
						</configuration>
					</execution>
				</executions>
			</plugin>
			<plugin>
				<groupId>pl.project13.maven</groupId>
				<artifactId>git-commit-id-plugin</artifactId>
				<configuration>
					<failOnNoGitDirectory>false</failOnNoGitDirectory>
				</configuration>
			</plugin>
		</plugins>
	</build>


	<repositories>
		<repository>
			<id>spring-milestones</id>
			<name>Spring Milestones</name>
			<url>https://repo.spring.io/milestone</url>
		</repository>
	</repositories>



http://localhost:8080/actuator/


# CRIAR BASHBOARD

Verificar questoes de seguranca depois com o Zuul.

O Spring boot e alimentado por esse yml

#### APLICATION.YML

management:
  endpoints:
    web:
      exposure:
        include: "*"
  endpoint:
    beans:
      enabled: true
    health:
      show-details: ALWAYS
  info:
    build:
      enabled: true


### criar os projetos baseado ao projeto Sample

  Projetos:
  - rs-user
  - rs-client
  - rs-product
  - rs-order
  - rs-order-item
