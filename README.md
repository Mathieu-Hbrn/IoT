# IoT
## Liste des objets connectés autours de vous
-Porte de la fab
-montre
-portable
-aspirateur robot
-lave linge
-sèche linge
-ordinateur / tablette
-chauffage / thermostat
-store
-cigarette électronique
-voiture
-moto
-gourde
-vélo
-console jeux
-bague
-balance
-chaussure / semelle
-lunette
-vêtements
-fourchette

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
  end
```
## Node-RED

-Earthquake

![{1CAE59E4-E52B-41EF-B7A7-27D4DB28B2AC}](https://github.com/user-attachments/assets/b9ae6915-d191-48aa-b914-d5f8b3afba9f)



- Dashboard

  ![{ACF34D60-99C7-4778-8729-3644C2A0DCDB}](https://github.com/user-attachments/assets/5da97db5-c14c-40d4-8d13-0ae033e74f1a)


  ![{765A2469-62E7-4D11-8631-E363A70D41A1}](https://github.com/user-attachments/assets/5be879c3-bbf3-4ed6-a012-f6206f0ce854)

  
