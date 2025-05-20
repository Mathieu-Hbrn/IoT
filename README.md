# IoT
## Liste des objets connectés autours de vous
-Porte de la fab

## Les Diagrammes

```mermaid
%% Example of sequence diagram
  sequenceDiagram
  actor User as User
  participant API as API
  participant Modele as Modele

  User ->> API: appel de l'API pour authentification<br>requète HTTP GET /login (avec email, password)
  API ->> Modele: Appel de la routine d'authentification<br>get_token(email, password)
  Modele ->> BDD : récupère le user correspondant à (email, HASH(password))<br>SELECT id, email, password FROM Users WHERE email=%s AND password=%s

  alt User OK
  BDD ->> Modele : User exist<br>(id, email, pwd, tel)
  Modele ->> API SMS: envoye code validation au tel par SMS
  API SMS->>Modele : confirmation envoi
  Modele->>API: page de confirmation SMS
  API->>User : Affichage page confirm SMS


  else email/password invalid
  BDD ->> Modele: pas de résultat
  Modele ->> API : réponse négative
  API->>User : erreur<br>status 401 Unauthorized
  end```

## Node-RED

![{1CAE59E4-E52B-41EF-B7A7-27D4DB28B2AC}](https://github.com/user-attachments/assets/b9ae6915-d191-48aa-b914-d5f8b3afba9f)

"msg.payload : Object
{"time":"2017-11-19T15:09:03.120Z","latitude":-21.5167,"longitude":168.5426,"depth":14.19,"mag":6.6,"magType":"mww","gap":21,"dmin":0.478,"rms":0.86,"net":"us","id":"us2000brgk","updated":"2017-11-19T17:10:58.449Z","place":"68km E of Tadine, New Caledonia","type":"earthquake","horizontalError":6.2,"depthError":2.8,"magError":0.037,"magNst":72,"status":"reviewed","locationSource":"us","magSource":"us"}"
