# TPJavaPipeLine - TAKKAL Fatima zahrae

## Objectif

Mettre en place un pipeline CI/CD automatisé permettant de compiler, tester et packager une application Java à chaque modification du code source.

## Technologies utilisées

- Java 21 : développement de l’application
- Maven : gestion de build et dépendances
- Jenkins : automatisation CI/CD
- Docker : conteneurisation de Jenkins
- GitHub : gestion du code source
- Webhook : déclenchement automatique du pipeline
- ngrok : exposition locale de Jenkins à Internet
  
## Architecture du pipeline CI/CD

Le pipeline d’intégration et de déploiement continus est déclenché automatiquement à chaque push sur GitHub.

Flux du pipeline :

- GitHub reçoit le push du code source
- Un Webhook notifie Jenkins
- Jenkins (dans un conteneur Docker) démarre le pipeline
- Maven compile le projet et exécute les tests unitaires
- Le projet est packagé en fichier .jar
- Le résultat est affiché dans Jenkins
  
## Structure du projet
<img width="388" height="144" alt="{828591E9-3797-4FBA-B385-B5E33B87D62C}" src="https://github.com/user-attachments/assets/3f69b1ca-35cf-4b58-863a-b1265fc16536" />

## Étapes de réalisation du projet
<img width="572" height="132" alt="image" src="https://github.com/user-attachments/assets/58e00938-210c-4954-8481-b4089eae9d4b" />

### 1. Création du projet Maven
<img width="526" height="409" alt="{82FA08D3-A2AD-44E2-A022-0D701117CD3A}" src="https://github.com/user-attachments/assets/66c80943-ea3d-42df-88b5-8b218f909b6e" />

<img width="433" height="73" alt="{376A2C11-4109-451A-A776-A87AA2B54E82}" src="https://github.com/user-attachments/assets/0269631f-96dc-4ce0-a850-91d7e1190252" />

<img width="554" height="213" alt="image" src="https://github.com/user-attachments/assets/6de3f0a7-a1cb-4f1f-a799-03455b2a3f5d" />

### 2. Compilation et tests
<img width="506" height="335" alt="{F9D53C96-D707-42CC-88C1-74C3F7F9498B}" src="https://github.com/user-attachments/assets/efbb555e-1f23-4484-bc0a-2449402f4c7d" />

## Jenkinsfile
<img width="305" height="416" alt="{9D51978D-B15E-4FF5-AA73-76793FEA18FF}" src="https://github.com/user-attachments/assets/db4652f7-0ce7-480b-8346-60913d779d39" />

## Dockerfile
<img width="495" height="184" alt="{08D3DDF1-D4DB-4D05-B364-B8D6E6836A71}" src="https://github.com/user-attachments/assets/6732eb42-0c81-42fa-a7f9-dac4c8a9df7d" />

<img width="518" height="684" alt="image" src="https://github.com/user-attachments/assets/ce3512a1-9858-488e-b1f1-1f26251cc146" />

<img width="520" height="128" alt="image" src="https://github.com/user-attachments/assets/8dfe85fb-45e2-430c-8b0b-21a3cba72187" />

<img width="555" height="102" alt="image" src="https://github.com/user-attachments/assets/5f2032fa-5fde-4d00-99a4-cad02379add5" />

### 3. Initialisation Git
<img width="554" height="214" alt="image" src="https://github.com/user-attachments/assets/eea61ab8-4795-4f3a-9d07-ee6f88968ef8" />

<img width="553" height="109" alt="image" src="https://github.com/user-attachments/assets/336b34f0-fcd5-4b84-9a56-54ff73b2ba4c" />



## Captures d execution

### 1. Vérification de Jenkins via Docker
La commande `docker ps` permet de vérifier que le conteneur Jenkins est bien actif.

### Résultat :
<img width="553" height="60" alt="image" src="https://github.com/user-attachments/assets/ea32a5de-8ab8-4153-ba97-12d387f03831" />

### 2. GitHub - Repository 
<img width="522" height="217" alt="image" src="https://github.com/user-attachments/assets/5fad0be8-233f-4663-9db0-2ec15db38888" />

#### Terminal - Git Push
Connexion du dépôt local vers GitHub et push du code source.
<img width="554" height="68" alt="image" src="https://github.com/user-attachments/assets/39671dd7-2d3e-48be-ac0d-3a78059595f5" />
<img width="559" height="173" alt="image" src="https://github.com/user-attachments/assets/8f58f89c-8343-46ad-8496-6822a93de08a" />

Depot GitHub contenant tous les fichiers du projet.
<img width="555" height="217" alt="image" src="https://github.com/user-attachments/assets/8fe50609-39ba-4ad9-9951-2fe1f8b914a6" />
### 3. GitHub - Webhook configure
Un Webhook est configuré pour notifier Jenkins à chaque push.
#### Etape 1 - ngrok tunnel public
ngrok expose Jenkins local sur Internet avec une URL publique temporaire.
<img width="816" height="36" alt="{BBC44EF4-7F42-480C-B0BA-DC28EE44F601}" src="https://github.com/user-attachments/assets/2848da46-c912-41af-8cfe-385c93cc0907" /> 
<img width="857" height="293" alt="{7E2F5A3E-ACD9-4674-A80D-0AD6951F43A2}" src="https://github.com/user-attachments/assets/ecdeca7f-2d2c-4f0e-a57f-7e4be91afadc" />

#### Configuration du Webhook 

<img width="771" height="634" alt="{B4D59FDB-9AED-4873-85FE-A47C4492AFCC}" src="https://github.com/user-attachments/assets/1826b785-a960-4e98-aff5-7368ca4b93bc" />
<img width="780" height="288" alt="{8D2BF259-2BF3-46A0-989F-D7F270BEA75E}" src="https://github.com/user-attachments/assets/3fd40f2e-ccf3-430f-8066-34249aa3e6d4" />
<img width="554" height="250" alt="image" src="https://github.com/user-attachments/assets/6ccd5894-91de-47d6-aa8a-df55a8828b49" />

### Jenkins - Pipeline Success
<img width="554" height="240" alt="image" src="https://github.com/user-attachments/assets/e24baa5f-cf8c-437c-9f5f-6d049a8036ee" />

### Jenkins - Déclenchement automatique via Webhook

Apres chaque `git push` sur GitHub, Jenkins detecte automatiquement
le changement via le Webhook et lance le pipeline sans intervention manuelle.
La capture ci-dessous montre le build #1 declenche automatiquement.

<img width="167" height="76" alt="{F077D307-F40A-4D5E-A1D7-A709865BFC08}" src="https://github.com/user-attachments/assets/fffb225c-6afe-4ef5-bffc-bb62c5e53353" />

<img width="553" height="231" alt="image" src="https://github.com/user-attachments/assets/9e0beb73-f33a-4a24-b2ff-0d97713ab325" />

### Jenkins Pipeline Success
<img width="1364" height="333" alt="{36077442-3F66-4EC8-86F8-848A701A1F1A}" src="https://github.com/user-attachments/assets/954ff363-3220-402c-8594-f431f41e79d4" />


## Résultat final

| Etape                                       |          Statut                          |
|----------------------------------------------------------------------------------------|
| Pipeline declenche automatiquement          | Succes                                   |
| Compilation Maven                           | Succes                                   |
| Tests unitaires                             | 1 test, 0 failures, 0 errors             |
| Package JAR                                 | javapipeline-1.0-SNAPSHOT.jar (2.06 KiB) |
| Archivage Jenkins                           | Succes                                   |


## Conclusion

Ce projet m’a permis de comprendre le fonctionnement d’un pipeline CI/CD complet basé sur Jenkins, Docker et GitHub.

Grâce à cette réalisation, j’ai appris à automatiser le cycle de vie d’une application Java (build, test, packaging) et à déclencher ces étapes automatiquement via un Webhook GitHub.

Ce TP illustre l’importance de l’intégration et du déploiement continus dans les projets modernes afin d’améliorer la qualité, la rapidité et la fiabilité du développement logiciel.



