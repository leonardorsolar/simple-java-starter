# aplicação Srping boot no Vscode

# java-basic

Uma das grandes utilização do Java é para criação de aplicações Web e APIs REST e um dos melhores frameworks para isso é o Spring-boot.

O Spring-boot surpreende pela facilidade para criar uma aplicação web em minutos e com pouco código. Na verdade, só o código que você está interssado de fato.

O modo mais fácil (que nos dá o código praticamente pronto) de criar uma aplicação com Spring-Boot, é utilizando o Spring Initializr.

# Spring-Boot initializr

1. Baixe o código do Spring-Boot configurado
   Acesse https://start.spring.io/, configure os metadados básicos do seu projeto, quais dependências do Spring nós vamos utilizar (Web no caso) e pronto! Agora você pode baixar um arquivo ZIP com o seu projeto Spring-boot configurado.

Gerenciador de dependências: Maven
A versão dom Spring-boot: vesao estável 3.0.6

Group(nome do pacote- nome da empresa invertido): com.aes
Artifact (nome do projeto): dslist
Name: dslist
Description: estudo java Spring Boot
Package name: com.aes.dslist
Packaging (linguagem java): jar
versão: 17 (LTS)

Adicionar dependências: 4

- Spring Web WEB
  Build web, including RESTful, applications using Spring MVC. Uses Apache Tomcat as the default embedded container.
- Spring Data JPA SQL (banco de dados)
  Persist data in SQL stores with Java Persistence API using Spring Data and Hibernate.
- H2 Database SQL (banco de dados em memória para testes)
  Provides a fast in-memory database that supports JDBC API and R2DBC access, with a small (2mb) footprint. Supports embedded and server modes as well as a browser based console application.
- PostgreSQL Driver SQL (banco de dados na nuven)
  A JDBC and R2DBC driver that allows Java programs to connect to a PostgreSQL database using standard, database independent Java code.

Generate Project

# 2. Descompacte o arquivo ZIP localmente

Após clicar em Generate Project, um arquivo ZIP será baixado para o seu computador, agora você precisa descompactar o arquivo em uma pasta local

# 3. Acesse a pasta descompactada pelo prompt de comando

Abra o prompt de comando e acesse a pasta descompactada. (cd <caminho da pasta>)

# 4. Instalar extensões de suporte ao Java

- Java Extension Pack ou Extension Pack Java
  Este pacote de extensões contém o essencial para sair desenvolvendo Java no vscode, tais como: Navegação de código, auto-complete, refactor, snippets de códigos principais, debbuger, entre outros.

- Spring Boot Extension Pack
  Este pacote de extensões contém o essencial para ajudar no desenvolvimento de projetos Spring Boot, tais como: Spring Boot Initializr (criação de projetos spring-boot), Spring Boot Dashboard (Aba do vscode que provê um explorador de projetos spring-boot no seu workspace), entre outros.

  -Spring Boot dashboard

  - lombok
  - vscode-icons
  - code runner

# reload no vscode : ctrl+shift+p

Após a instalação destes plugins, lembre-se de abrir a paleta de comandos e mandar um Reload Window (ctrl+shift+p => windows/linux ou cmd+shift+p => mac) e escreva Reload Window + Enter.
apareceu no lado esquerdo inferior: java projects
mavem

# java overview : ctrl+shift+p

Para criar o prokejeto no vscode

# alteração no arquivo pom.xml

<build>
		<plugins>
    inserir aqui o Trechos de código Plug-in Maven
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>

Trecho de código Plug-in Maven
<plugin>
<groupId>org.apache.maven.plugins</groupId>
<artifactId>maven-resources-plugin</artifactId>
<version>3.1.0</version> <!--$NO-MVN-MAN-VER$ -->
</plugin>

Opcional:
Faça apenas uma pequena alteração no arquivo pom.xml, na seção de dependências, mude o artifactId do org.springframework.boot de: spring-boot-starter para: spring-boot-starter-web. Isso fará com que o maven busque o artefato que possui o necessário para trabalhar com REST APIs ou MVC.

# 4. Baixe as dependências do projeto

Com o projeto criado, vá no vscode e abra a pasta que acabamos de criar. O vscode irá tentar inicializar as extensões, e atualizar as dependências Maven suportar o projeto, então, aguarde até que o processo termine antes de continuar:

atualização no menu inferior do vscode

# 5 Projeto

Para criar o projeto no vscode: src/main

## DslistApplication:

src/main/java/com/aes/dslist/DslistApplication.java
criado a classe principal

## application.properties:

src/main/resources/application.properties
inserir os dados do banco de dados

## DslistApplicationTests.java

src/test/java/com/aes/dslist/DslistApplicationTests.java
criado um teste

## pom.xml

com arquivo aberto é possível adiconar novas dependências
adicionar do start spring io:
clique com o botão direito no arquivo pom.xml em add starters

## target

local que será gerado os arquivos de build arquivo jar

# Inicializar o projeto: incializar o servidor

clique em run na barra supeior
clique em run no codigo

Tomcat initialized with port(s): 8080 (http)

# Criação da sua primeira classe

src/main/java/com/aes/dslist/controller.java

@Rest - clique em control espaço para o intelicence
public class HelloController {

podemos agora criar métodos para get, post delete...

GetMapping - clique em control espaço para o intelicence

dev-se retornar no DslistApplication e executar: run

# Visualização no browser:

vá até o browser:
http://localhost:8080/

fontes:

https://www.youtube.com/watch?v=dkmlOi_MNb4

https://code.visualstudio.com/docs/java/java-spring-boot

forma básica:
https://www.alura.com.br/artigos/desenvolvendo-aplicacoes-java-vs-code

https://dicasdejava.com.br/spring-boot-como-criar-a-estrutura-de-uma-aplicacao-web-do-zero-com-spring-initializr/

https://medium.com/danielpadua/java-spring-boot-vscode-9ef9b8a263cd

setup inicial do ambiente, que é o Coding Pack for Java. Nesse pacote de instalação já estão incluídos os seguintes itens:

JDK (Java Development Kit - pode variar a versão, de acordo com a data que você fizer o download, mas geralmente é uma versão LTS, ou seja, com suporte de longo prazo. No momento da publicação desse artigo a versão é a 17);
VS Code
Extensões essenciais Java (ou Java Extension Pack)
