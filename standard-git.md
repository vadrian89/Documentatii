# Standardul folosit in folosirea git va fi trecut aici.  
## Branch-urile proiectelor: ##
-   [**master**](#master) -> branch-ul de lucru;
-   [**test**](#test) -> branch-ul de test;
-   [**pre**](#pre) -> branch-ul de pre-producție;
-   [**pro**](#pro) -> branch-ul de producție;

### master ###
Branch-ul principal de lucru, aici se vor face pull-request-urile de lucru pentru a putea fi trimise catre test.
Se va face pull request în unul din următoarele cazuri:
-   s-a adăugat o funcționalitate nouă;
-   s-a rezolvat o problemă;
-   s-a eliminat o funcționalitate;
-   e necesară testarea pe server;
-   cel care a lucrat la cod lipsește mai mult de 2 zile;

### test ###
Codul din acest branch va folosit în mediile de testare.

### pre ###
Branch-ul de **pre** e pentru a fi folosit în mediile de pre-producție, pentru a se testa funcționalitățile și tranziția codului într-un mediu apropiat celui de producție.

### pro ###
Codul din acest branch trebuie să fie funcțional pentru mediile oficiale de producție.

## Workflow ##
### Faza de dezvoltare ###
1.  Fiecare programator va face pe propriul *fork* al proiectului.
2.  Când va fi nevoie, programatorul, va face *pull request* pentru a adăuga codul în branch-ul **master**.
3.  Colegii de echipă vor revizui codul din pull request și vor lăsa comentariu cu *Aprobat* sau *Neaprobat*. În caz de neaprobare se va explica motivul.
    1.  În caz de neaprobare, programatorul va implementa problemele discutate cu colegii de echipă și va actualiza pull request-ul.
    2.  În caz de aprobare, se va face *merge* de către responsabilul proiectului.
4.  Se va deschide issue cu cerere de *pull request* **master** -> **test** pentru a trece la faza de testare.
5.  Se va face *pull request*, revizuire modificări și *merge* de către responsabilul proiectului.
### Faza de testare inițială ###
6.  Se vor testa toate modificările de către programatorul care a inițiat pull request-ul către branch-ul master.
    1.  Dacă ceva nu funcționează, programatorul, va lăsa comentariu în issue-ul original și va relua pașii necesari pentru a ajunge la punctul 6.
    2.  Dacă totul funcționează se va deschide issue cu cerere de *pull request* **test** -> **pre** pentru a trece la faza de testare în pre-producție. Issue-ul din faza de testare inițială se va închide.
7.  Se va face *pull request*, revizuire modificări și *merge* de către responsabilul proiectului.
### Faza de testare pre-producție ###
8.  Se va testa ca aplicația să nu fi fost afectată de *merge*, se vor testa toate modificările făcute și o verificare generală a proiectului pentru a elimina orice problemă de către toți membrii echipei.
    1.  Dacă ceva nu funcționează se va lăsa comentariu în issue-ul de la pasul 6.2 iar programatorul care a făcut modificările va relua pașii necesari pentru a ajunge la punctul 8.
    2.  Dacă totul funcționează se va deschide issue cu cerere de *pull request* **pre** -> **pro**.
9.  Se va face *pull request*, revizuire modificări și *merge* de către responsabilul proiectului. Issue-ul din faza de testare pre-producție se va închide.
### Membrii echipei vor efectua teste ale proiectului cu versiunea de producție pentru a se asigura că nu există probleme. ###

## Informații adiționale workflow ##
-   membri echipei care lucrează la proiect vor fi trecuți în fisierul principal README.md sub categoria **Componența echipei**;
-   responsabilul proiectului va fi trecut in fisierul principal README.md sub forma **Responsabil: Nume Prenume**;
-   nu este obligatorie aprobarea unui membru al echipei, dacă acesta lipsește de la locul de muncă, indiferent de motiv: concediu/învoire/nemotivat;
-   in lipsa responsabilului de proiect oricare membru al echipei ce are drept poate face *pull request* și *merge*, doar până la faza de **pre-producție** și doar cu minimum 2 aprobări de la alți membri ai echipei;
-   responsabilul de proiect poate oferi drepturi administrative în funcție de nevoi;
-   nu vor lucra mai mult de 1 persoană pe același fișier, pentru a evita probleme ulterioare; se va comunica constant în echipă;
-   excepție de la regulile workflow-ului descris e documentația;

## Standard denumire branch ##
Pe lângă denumirile standard master/test/pre/pro se vor crea diferite branch-uri doar la nevoie:
1.  Branch-ul să aibă o denumire descriptivă;
2.  Denumirea trebuie să fie de forma: **nume-branch**;

## Standard commit-uri ##
1.  Titlurile commit-urilor trebuie să fie descriptive și scurte; **Prima linie din commit e titlul**;
2.  Corpul commit-ului trebuie să descrie exact ce s-a modificat;

## Standard issue-uri ##
Pentru a se putea selecta mai ușor rezolvarea issue-urilor acestea vor avea titluri standarde care vor descrie importanța lor, precum
și etichete specifice.
1. Eroare de producție -> Etichetă: Urgent
2. Cerere pull request PRE/PRO -> Etichetă: Pre2Pro
3. Cerere pull request TEST/PRE -> Etichetă: Test2Pre
4. Cerere pull request Master/TEST -> Etichetă: Master2Test
5. Cerere funcționalitate nouă -> Etichetă: Request
6. Bug test -> Etichetă: Important
7. Bug pre -> Etichetă: Important
8. Bug pro -> Etichetă: Important
Dacă nici unul din titluri nu desscrie problema celui care deschide issue se vor folosi următoarele standarde:
9. Cerere: <text scurt și descriptiv> -> Etichetă: Request/TODO
10. Problemă: <text scurt și descriptiv> -> Etichetă: Important

## Standard etichete ##
Etichetele vor avea următoarele culori, în cod hex:
-   Urgent: #ff1100
-   Important: #fcf526
-   Request: #9700a8
-   Pre2Pro: #000ea8
-   Test2Pre: #0094a8
-   Master2Test: #00a822
-   TODO: #5100a8
