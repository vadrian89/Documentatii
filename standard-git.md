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
    1.  Dacă ceva nu funcționează se va lăsa comentariu în issue-ul de la pasul 8b iar programatorul care a făcut modificările va relua pașii necesari pentru a ajunge la punctul 8.
    2.  Dacă totul funcționează se va deschide issue cu cerere de *pull request* **pre** -> **pro**.
9.  Se va face *pull request*, revizuire modificări și *merge* de către responsabilul proiectului.
### Membrii echipei vor efectua teste ale proiectului cu versiunea de producție pentru a se asigura că nu există probleme. ###
