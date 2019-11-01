# Standardul folosit in SQL va fi trecut aici. #
Forma va fi: \<element\>: \<sintaxa\>    

Schema: NUME_PROIECT  
Tabela: (2 - 4 caractere din schema)\_(MA|TR|HS)\_NUME_TABELA
-   MA -> tabele master
-   TR -> tabele tranzactionale
-   HS -> tabele istoric (history)
Nume Coloana: (2 - 4 caractere din nume tabela)\_NUME_COLOANA
Secventa: SQ_NUME_COLOANA
Constraint: NUME_COLOANA_(FK|NN|UQ)
-   FK -> cheie straina (foreign key)
-   NN -> nenul (not null)
-   UQ -> unic (unique)

Exemplu:  

```SQL
Nume proiect: GEST_APP
Schema: GEST_APP
Tabela: GA_MA_TABELA_MASTER
Coloana: TM_O_VALOARE
/* TM -> Tabela Master */
Secventa: SQ_CHEIE_PRIMARA
Constraint: FK_CHEIE_STRAINA
```
