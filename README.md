# Spring_Boot_app
un exemple d'application Spring Boot avec spécifications JPA
#Le projet demo.rest est une application java spring-boot qui implémente une template jdbc et utilise la technologie REST
Spring Boot est un nouveau framework conçu pour simplifier le démarrage et le développement de nouvelles applications Spring.  Boot se veut être un acteur majeur dans le secteur croissant du développement d'applications rapide.
Spring Boot soutient des conteneurs embarqués (embeddes containers).Cela permet des application web d’exécuter indépendamment sans déploiement sur Web Server.
Spring Boot permet aussi d’intégrer facilement avec l’application des écosystèmes comme Spring JDBC.
La structure générale du projet :
-	src :
       -main.java.com.example.demo --> YassinApplication.java
                 .com.example.demo.person.service-->Person.java
						                                     -->PersonEntity.java
						                                     -->PersonEntityManagerFromFactory.java
						                                     -->PersonJdbcTemplate.java
                 .com.example.demo.rest-->HelloWorldRestController.java
				                               -->PersonRestController.java  
      -main.java.resources.application.proprieties

      -testjava com example demorest ApplicationTests.java
					        
       - target
      - pom.xml

Points à noter:

- YassinApplication.java:
Cette classes est annotées par   @SpringBootApplication. Cette annotation  équivaut à utiliser  @Configuration, @EnableAutoConfiguration et  @ComponentScan avec ses attributs par défaut.
Donc  @SpringBootApplication vous aide de configurer automatiquement Spring, et automatiquement scanner (Scan) le projet intégral afin de découvrir des composants de  Spring

L’application est lancé par l'exécution de la classe  YassinApplication. C’est le main()de l’application Spring Boot ;elle declenche la configuration automatique de l’infrastructure Spring.

-Person.java :
C’est une classe qui permet la définition des attributs et des méthodes de l’objet Person.
En utilisant les spécifications JPA on ajoute les attributs à la BD :
            @Id et @Generatevalue pour créer la clé primaire
            @Column : pour spécifier la colonne d’attribut dans la BD.

- PersonEntity.java:
Pour Spring Data JPA Entity Manager permet l’accès rapide aux données et permet l’interaction avec ‘’ persistence context’’. Elle permet une gestion explicite et facile des requetés.


- PersonJdbcTemplate.java:
Cette classe implémente une template jdbc pour la connexion avec la base de données. On définit les paramètres de connexion et ensuite on specifie la requête SQL

- HelloWorldRestController.java et  PersonRestController.java  :
Elles représentent les classes contrôleurs de l’application qui définissent les URI des vues avec la technique mapping REST 

- application.proprieties: C’est le fichier qui définit l’hibernate de JPA et url de l’application .

- pom.xml : le fichier où on définit les dépendances de l’application.
