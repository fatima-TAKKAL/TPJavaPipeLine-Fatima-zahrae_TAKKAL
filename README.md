# TPJavaPipeLine - TAKKAL Fatima zahrae

## Description
L'objectif de ce TP est de mettre en place un pipeline CI/CD complet.
Chaque modification du code source pushee sur GitHub declenche automatiquement
une serie d'etapes dans Jenkins : compilation, tests unitaires, packaging et archivage.
Cela permet de detecter les erreurs rapidement et de livrer une application
stable et testee de maniere automatique.

## Technologies utilisees
- **Java 21** : langage de programmation utilise pour developper l'application
- **Maven 3.8.7** : outil de gestion de build, compile le code et execute les tests automatiquement
- **Jenkins** : serveur CI/CD qui ecoute et reagit aux push GitHub, lance le pipeline automatiquement
- **Docker** : conteneurise Jenkins pour l'isoler et le rendre portable sur n'importe quelle machine
- **GitHub Webhook** : notifie Jenkins a chaque push de code pour declencher le pipeline
- **ngrok** : cree un tunnel public temporaire pour exposer Jenkins local a GitHub.

## Structure du projet
TPJavaPipeLine/
├── Jenkinsfile   <- script du pipeline CI/CD
├── Dockerfile    <- image Docker de l application
├── pom.xml       <- configuration Maven
└── src/
├── main/java/com/example/App.java
└── test/java/com/example/AppTest.java
## Captures d execution
### Jenkins - Pipeline Success
<img width="553" height="376" alt="image" src="https://github.com/user-attachments/assets/42343cb9-eaef-4624-bb51-9126141b9937" />
<img width="554" height="478" alt="image" src="https://github.com/user-attachments/assets/d3ccdf70-9f6a-45b6-a962-a3e9eabb5327" />
### GitHub - Repository
<img width="554" height="261" alt="image" src="https://github.com/user-attachments/assets/6342d4d8-6b69-4ede-81aa-e97f6ef59bf1" />
<img width="554" height="68" alt="image" src="https://github.com/user-attachments/assets/39671dd7-2d3e-48be-ac0d-3a78059595f5" />
<img width="559" height="173" alt="image" src="https://github.com/user-attachments/assets/e415392b-0104-46db-8ca5-16e77d65c3b2" />
<img width="554" height="256" alt="image" src="https://github.com/user-attachments/assets/2cb9b15d-b8d5-47ba-ac08-2443ad559ed7" />
### GitHub - Webhook
<img width="441" height="215" alt="image" src="https://github.com/user-attachments/assets/c2acb40d-1190-4e49-9ad7-0a426a58de61" />


