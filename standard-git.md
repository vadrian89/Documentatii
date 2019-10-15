# Standardul folosit in folosirea git va fi trecut aici.  
## Branch-urile proiectelor: ##
-[**master**](#master) -> branch-ul de lucru;
-[**test**](#test) -> branch-ul de test;
-[**pre**](#pre) -> branch-ul de pre-producție;
-[**pro**](#pro) -> branch-ul de producție;

## master ##
Branch-ul principal de lucru, aici se vor face pull-request-urile de lucru pentru a putea fi trimise catre test.
Se va face pull request în unul din următoarele cazuri:
-s-a adăugat o funcționalitate nouă;
-s-a rezolvat o problemă;
-s-a eliminat o funcționalitate;
-e necesară testarea pe server;
-cel care a lucrat la cod lipsește mai mult de 2 zile;

## test ##
Codul din acest branch va folosit în mediile de testare.

## pre ##
Branch-ul de **pre** e pentru a fi folosit în mediile de pre-producție, pentru a se testa funcționalitățile și tranziția codului într-un mediu apropiat celui de producție.

## pro ##
Codul din acest branch trebuie să fie funcțional pentru mediile oficiale de producție.
