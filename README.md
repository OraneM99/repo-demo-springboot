
# Documentation Spring

## 1. Qu'est-ce que Spring ?

**Spring** est un projet open source qui fournit une approche simplifiée et modulaire de la création d’applications avec Java.

Le nom Spring seul fait généralement référence à l’infrastructure d’application elle-même ou à l’ensemble du groupe de projets, ou modules. Java Spring Boot est un des modules spécifiques qui est créé en tant qu’extension de l’infrastructure Spring.

L'objectif principal est de simplifier la complexité du développement Java, notamment via :
- La gestion des objets
- La configuration
- Les dépendances
- L'accès aux données
- La création d'API

Spring agit comme un chef d'orchestre qui gère les objets à notre place.

---
## 2. Quelle est la différence entre Spring et Spring Boot ?

|Spring|Spring Boot|
|---|---|
|Framework complet|Extension de Spring|
|Configuration manuelle|Configuration automatique|
|Plus flexible|Plus rapide à démarrer|
|Plus verbeux|Moins de code|

---
## 3. Qu'est-ce que l'inversion de contrôle ?

L'inversion de contrôle est un principe où ce n'est plus le code qui crée les objets, mais le framework.

Exemple :

```java
@Autowired
UserService userServce;
```

C'est Spring qui injecte l'objet.

---
## 4. Qu'est-ce que l'injection de dépendance ?

L’injection de dépendances consiste à fournir à un objet ce dont il a besoin au moment de sa création, plutôt que de le laisser créer ses outils lui-même. C’est le framework (le conteneur) qui s'occupe de la livraison, ce qui rend le code plus flexible et facile à tester.

---
# Mini-projet : Hello World

Pour créer un "Hello World" en Spring Boot, il nous faut initialiser le projet via **Spring Initialzr**.

![](images/brief16_spring_initializr.png)

Voici l'affichage de notre premier "Hello World" :

```java
@SpringBootApplication  
public class DemoApplication implements CommandLineRunner {  
  
    public static void main(String[] args) {  
        SpringApplication.run(DemoApplication.class, args);  
    }  
  
    @Override  
    public void run(String... args) throws Exception {  
        System.out.println("Hello World !");  
    }  
}
```

Rendu :

![](images/brief16_screen_spring.png)

---
## Partie 1 : Pourquoi et quand utiliser Spring Boot

### Pourquoi utiliser Spring Boot

**1. Configuration Automatique** : Atout majeur de Spring Boot, il configure automatiquement la connexion à une base de données. Pas besoin d'écrire des fichiers XML ou des classes de configuration.

**2. Dépendances simplifiées** : Au lieu de chercher des bibliothèques compatibles entre elles, on ajoute une seule qui importe tout ce qu'il faut pour créer une API par exemple.

**3. Serveur embarqué** : Installation et configuration automatique de son propre serveur web. L'application devient un simple fichier `.jar` qu'on lance comme un petit logiciel.

---
### Quand utiliser Spring Boot

Il est devenu le standard pour le développement Java moderne, mais voici pourquoi l'utiliser :

- **Pour des micro-services** : grâce à sa rapidité de déploiement cela facilite la création de petits services indépendants qui communiquent entre eux.
- **Pour les API REST** : outil le plus efficace si on doit créer un backend pour une application mobile ou un site React/Angular.
- **Pour des applications d'entreprise robustes** : offre toute la sécurité et la puissance de l'écosystème Spring pour gérer les transactions bancaires ou des données complexes.

---
### Quand ne pas utiliser Spring Boot

Il est préférable d'éviter d'utiliser Spring Boot quand on a juste besoin d'un petit programme Java. Par exemple, un calcul simple et qui s'arrête, Spring Boot consommera plus de mémoire au démarrage qu'au moment du calcul.

---
### En résumé

On utilise Spring Boot dès qu'on veut créer une application web ou un service backend de manière moderne, rapide et professionnelle sans perdre de temps dans le code technique.

---
## Partie 2 : Étapes clés de tout projet Spring Boot

Au lieu de créer les dossiers à la main, on utilise presque toujours **Spring Initializr**.
- **Le choix du moteur** : Maven ou Gradle.
- **Les dépendances** : On coche tout ce dont tu as besoin (Web, Base de données, Sécurité).
- **Le résultat** : Un projet structuré prêt à être importé dans l'IDE (IntelliJ, VS Code ou Eclipse).

On configure le fichier `application.properties`, c'est le centre de contrôle. Au lieu de coder en dur les paramètres, on les centralise dans `src/main/resources/application.properties`.

C'est dans ce fichier qu'on défini notre port du serveur ou les identifiants de la base de données.

Dans un projet Spring Boot, on organise généralement le code en trois couches pour qu'il reste propre :
- **Controller** : Reçoit la requête HTTP (l'aiguilleur).
- **Service** : Contient la logique métier (les calculs, les règles).
- **Repository** : Communique avec la base de données.

---
# Différents termes rencontrés

- **Quelle est la structure du projet créé ?**

La structure du projet suit la convention standard de Java avec le code source dans `src/main/java`, les configurations dans `src/main/resources` et les tests dans `src/test/java`.

- **Qu'est-ce que Gradle et Maven ?**

Ce sont des gestionnaires de dépendances qui gèrent le téléchargement des bibliothèques (dépendances) et la compilation du projet.

- **C'est quoi un package ?**

C'est un dossier servant à organiser les classes Java par thématique et à éviter les conflits de noms au sein du code.

- **Quelle est la différence entre un war et un jar ?**

Le JAR est une archive autonome incluant son propre serveur web tandis que le WAR est un format destiné à être déployé sur un serveur externe déjà installé.