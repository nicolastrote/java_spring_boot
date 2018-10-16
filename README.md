# JAVA_SPRING
Preparation pour un environnement SPRING BOOT

## INSTALLATION JAVA JDK 8
Machine virtuel et espace de dev
https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html
```$ java --version```

## INSTALLATION HOMEBREW
Gestionnaire de paquets
```/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"```
```$ brew -v```

## INSTALLATION  GROOVY
Groovy est le nom d'un langage de programmation orienté objet destiné à la plate-forme Java
```
$ brew install groovy
$ groovy -v
```

## INSTALLATION GRADLE
Gradle est un moteur de production fonctionnant sur la plateforme Java. Il permet de construire des projets en Java, 
```
$ brew install gradle
$ gradle -v
```

## INSTALLATION SPRING-BOOT-CLI
```
$ brew tap pivotal/tap
$ brew install springboot
$ spring version    (Spring CLI v2.0.5.RELEASE)
$ spring help run
$ spring init --list   (Service capabilities)
```

## PREPARER SON ENVIRONNEMENT GITHUB
* creer un repo sur github JAVA
* mkdir /home/USER/Documents/_coding && cd /home/USER/Documents/code
* ```git clone https://github.com/nicolastrote/java_spring.git```

## Running Applications with the CLI
Creer le dossier hello_groovy, et fichier hello.groovy avec le contenu (cf source)
Puis lancer la compilation
```
$ JAVA_OPTS=-Xms256m -Xmx2048m spring run hello.groovy -- --server.port=9000
```
Le resultat s'affiche sur http://localhost:9000

## SDK MAN
Software development kit manager (ancien nom GVM) idéal pour les projets JAVA. Mais sous OSX on utilise HOMEBREW, donc pas nécessaire.

## INSTALLATION INTELIJ FULL VERSION ET EXPL
* nouveau projet avec Spring Initializr
* Type project: Gradle
* language: Groovy
* springboot version peut etre updaté en cliquant dessus
* dependencies: Web

# EXEMPLE 1 : GROOVY_APP
* creer le fichier app.groovy
```
@RestController
public class HelloWord {
	@RequestMapping("/")
	public String home() {  "hello world" }
}
```
Puis lancer la compilation
```
$ JAVA_OPTS=-Xms256m -Xmx2048m spring run app.groovy -- --server.port=9000
```
le code est similaire en langage groovy à  :
```
@RestController
class HelloWord {
	@RequestMapping("/")
	public String home() {  "hello world" }
}
```

# EXEMPLE 2 : HELLO_SPRING_BOOT_2
Pour créer un projet et sa structure sous spring : 
* une 1e solution : start.spring.io
* une 2e soution : spring init -d=web  my-app
* une 3e solution : curl start.spring.io
  en bas du retour de la commande, il y a les exemples comme
  ```curl https://start.spring.io/starter.zip -o demo.zip```
* une 4e : avec IntelliJ
  - création avec les options par défaut sous spring initialzr (java, maven) et ajouter import WEB
  - ne pas tenir compte du fichier : DemoApplication
  - creer à côté le fichier HomeController:
  ```
  	package com.example.demo;
	import org.springframework.web.bind.annotation.RequestMapping;
	import org.springframework.web.bind.annotation.RestController;
	@RestController
	public class HomeController {
    @RequestMapping("/")
    public String home() { return "hello spring boot 3"; }
}
  ```

# EXEMPLE 3 : JAVA BUILD TOOLS (ant/maven/gradle)








# SOURCES
* https://www.udemy.com/spring-boot-getting-started
* https://docs.spring.io/spring-boot/docs/current/reference/html/zetting-started-installing-spring-boot.html
* Running Applications with the CLI : https://docs.spring.io/spring-boot/docs/current/reference/html/cli-using-the-cli.html#cli-run
